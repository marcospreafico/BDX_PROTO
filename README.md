# BDX_PROTO

This is the set of files required to generate in GEMC the geometry of BDX-PROTO

Files .pl contain the script to gemerate ingredients for GEMC simulation:
- bank.pl  --> contain the variables that are saved in output files 
- geometry.pl --> contain the geometry of the detector 
- hit.pl  --> contains the hit processes (i.e. how each component of the detector transforms GEANT quantities in signal)
- materials.pl --> contains information on the materials available
- proto.pl --> script to run to generate all the .txt files required by GEMC 

config_proto.dat contains the configuration parameters for the full simulation. Since all the parameters are fixed, the only quantity that can be changed from the configuration is the layout of the crystal: to generate the prototype with cyrstals along the beam direction set "vertical_crystal" to 0, otherwise to have them perpendicular to the beam direction set it to 1.  

test.gcard is a premade gcard to run GEMC using the prototype geometry.

To generate files for GEMC you need to run the command 
./proto.pl config_proto.dat

To run gemc use: 
/path/to/gemc test.gcard [your options]
