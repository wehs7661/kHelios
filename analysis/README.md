This folder houses analysis programs that may be useful during the course of using Helios
- `helang.f90` --- calculate the angle between two vectors based on their spherical coordinates Phi (azimuth) and Theta (longitude)
  - compile:
    `gfortran helang.f90 -o helang.o`
  - usage: (phi1 and theta1 are spherical coordinates of the first vector; phi2 and theta2 are spherical coordinates of the second vector)
  Input and output values are in degrees.
    `./helang2.o [phi1] [theta1] [phi2] [theta2]`

- `helang2.f90` --- interactive version of helang.f90 above
  - compile:
    `gfortran helang.f90 -o helang2.o`
  - usage:
    input and output values are in degrees
    `./helang2.o`