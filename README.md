# kHelios
This repository is mainly for maintaining the notes for the software kHelios developed by Dr. Coutsias from Stony Brook University. 

kHelios derives helical parameters from a set of points using geometry, linear algebra and vector analysis. (Ref: [Characterization of Biomolecular Helices and Their Complementarity
Using Geometric Analysis](https://pubs.acs.org/doi/10.1021/acs.jcim.6b00721).)

This software requires bash (shell) and fortran compiler (gfortran). If you have a different fortran compiler, you can manually edit `install_helios.sh` to suit.

To install this software, simply type:
```
bash install_helios.sh
```

To run the script, one could run the following command:
```
$KHELIXHOME/bin/helios.o Ktest.input
```
where `Ktest.input` can be replaced by any input file that looks like the one below (`/test/alpha-helix/input`):
```
inputhelix alpha_-57_-47.pdb
helixout_name KHelix.32.out
coord_type 1
num_grid 360
natoms 32
nframes 1
grid_phi_beg 75
grid_phi_end 95
grid_theta_beg 0
grid_theta_end 20
helix_atom_names CA
print_to_plot 1
```
One could also save `$KHELIXHOME/bin/helios.o` as an alias in `.bashrc` to more conveniently use the code. Based on this, the following script could be useful to run kHelios for all the PDB files present in the working directory:
```bash
#!/bin/bash

for i in $(ls *pdb); do
cat > input << EOF
inputhelix $i
helixout_name kHelix.$i.out
coord_type 1
num_grid 360
natoms 32
nframes 1
grid_phi_beg 0
grid_phi_end 180
grid_theta_beg 0
grid_theta_end 180
helix_atom_names CA
print_to_plot 1
EOF
$KHELIXHOME/bin/helios.o input
done
```
As a result, helical parameters will be printed to the output file(s) and one could use those parameters to build a PDB for an ideal helix model using other tools (such as [`cg_openmm`](https://github.com/shirtsgroup/cg_openmm/blob/master/examples/helix_modeling/optimize_nonbonded_parameters/optimize_LJ_constrained.py))