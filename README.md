These scripts are provided to help the proper set-up of a debian based system
to allow compilation of the sources for:<br>
libindi, 
indi-3rd-party, 
stellarsolver, 
libXIFS, 
and kstars

Best is to install these scripts into your ~/bin directory

My scripts assume French as locale so if you have different locale exit bkstars for the git response 'Déjà à jour." that will be different on your system 

# Invoke as "indi Projects"
 It will set-up the environement to compile the indi and kastar sources
 The script will create the following tree into your home directory

 Projects/
 ├── build
 ├── indi
 ├── indi-3rdparty
 ├── kstars
 ├── kstars-build
 ├── libXISF
 └── stellarsolver

 It then will install all dependencies for idi, indi-3rdparty, kstars
 and install libXISF

 After that your system is ready for the compilation of:
# indi
 ===============================
 cd ~/Projects/indi
 ./developer-build.bash
 cd build
 sudo make install
 cd ..
 rm build
 sudo rm -r /dev/shm/indi-build
 -------------------------------

# indi-3rdparty libs
 ===============================
 run the companion script "build3"
 -------------------------------

# indi-3rd-party
 ===============================
 run the companion script "3rd"
 -------------------------------

# stellarsolver
 ===============================
 is part of the build process handlled by the "bkstar" script
 -------------------------------

# libXIFSF
 ===============================
 cd ~/Projects/libXISF
 git pull
 cmake -B build -S .
 cmake --build build --parallel
 sudo cmake --install build

 -------------------------------

# and kstars
 ===============================
 run the companion script "bkstars"
 -------------------------------

 All the scripts assume you have ebougth RAM available (Min 4Gbyte)
 since everything is compiled in /dev/shm avoiding SSD usage
