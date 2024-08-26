These scripts are provided to help the proper set-up of a debian based system
to allow compilation of the sources for:<br>
libindi, <br>
indi-3rd-party, <br>
stellarsolver, <br>
libXIFS, <br>
and kstars<br>

Best is to install these scripts into your ~/bin directory<br>

My scripts assume French as locale so if you have different locale edit bkstars for the git response 'Déjà à jour." that will be different on your system <br>

# Invoke as "indi Projects"<br>
 It will set-up the environement to compile the indi and kstar sources<br>
 The script will then create the following tree into your home directory<br>

 Projects/<br>
 ├── build<br>
 ├── indi<br>
 ├── indi-3rdparty<br>
 ├── kstars<br>
 ├── kstars-build<br>
 ├── libXISF<br>
 └── stellarsolver<br>

 It then will install all dependencies for indi, indi-3rdparty, kstars<br>
 and install libXISF<br>

 After that your system is ready for the compilation for:<br>
# indi<br>
 cd ~/Projects/indi<br>
 ./developer-build.bash<br>
 cd build<br>
 sudo make install<br>
 cd ..<br>
 rm build<br>
 sudo rm -r /dev/shm/indi-build<br>

# indi-3rdparty libs<br>
 run the companion script "build3"<br>

# indi-3rd-party<br>
 run the companion script "3rd"<br>

# stellarsolver<br>
 is part of the build process handlled by the "bkstar" script<br>

# libXIFSF<br>
 cd ~/Projects/libXISF<br>
 git pull<br>
 cmake -B build -S .<br>
 cmake --build build --parallel<br>
 sudo cmake --install build<br>

# kstars<br>
 run the companion script "bkstars"<br>

 All the scripts assume you have ebougth RAM available (Min 4Gbyte)<br>
 since everything is compiled in /dev/shm avoiding SSD usage<br>
