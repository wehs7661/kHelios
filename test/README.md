This folder houses a variety of test cases used to validate the method. Some of the descriptions below are verbose, in case someone reading this file is not a structural biologist and is too lazy to google every fifth word I use.

### 1. The folder `./NievergeltsTLS/`
Yves Nievergelt published a very interesting article entitled ["Fitting helices to data by total least squares" (Journal: Computer Aided Geometric Design; Year: 1997; Volume: 14; Pages: 707-718)](https://www.sciencedirect.com/science/article/pii/S0167839696000581). In that article, Nievergelt presented a method "similar" to that used in Helios. Notably, Table 1 of the article presents the Cartesian coordinates of 10 points of an irregular helix that sweeps 90 degrees (yes, it looks an arc). The radius of the helix the points trace is 195 Arbitrary Unites (AU) and the pitch of the helix is 594 AU. This folder contains the following subdirectories:
- The folder `./axis-constraints/`
This directory tests Helios while using constraints on the orientation of the helix axis by bounding the range of Phi and Theta.
    
- The folder `./no-constraints/`
This directory tests Helios without any constraints (all five helical parameters are free).
    
### 2. The folder `./protein_secstruct_setup/`
Proteins are polymeric chains of amino acids linked together by an amide bond. The amide bond is interesting geometrically, and of course chemically, because the torsion angle it subtends with the amino acids it bonds is rigid (double bond character). So, the chains of amino acids that make up proteins act more like polygonal chains than floppy rope (they're said to be constrained). Who cares? These constraints are geometric, and combined with the underlying chemistry (H-bonding between the N-H of one amide and the C=O of another), the chains of amino acids that make up proteins tend to adopt particular geometries, the major
one being a helix. Depending on the torsion angles within the peptide chain, slightly yet detectably different types of helical geometries --
"helical secondary structure elements" -- are observed in proteins: alpha, pi and 3_10.
    
### 3. The folder `./alpha-helix/`
This directory houses tests in which the number of CA atoms of three variants of the alpha helix are required to derive the known reference helical parameters of alpha helical secondary structure elements.