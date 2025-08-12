RTKLIB-EX-LINUX (a fork from rtkexplorer): A version of RTKLIB optimized for low cost GNSS receivers (single, dual, or triple frequency), especially u-blox receivers and based on RTKLIB 2.5.0. This software is provided “AS IS” without any warranties of any kind so please be careful, especially if using it in any kind of real-time application. 


The latest version of the user manual is at: https://rtkexplorer.com/pdfs/manual_demo5.pdf

   
WINDOWS: To build and install code for with Windows Embarcadero compiler but is not the focus. There is attempt to keep it synchrnoized.

For linux, use QT Creator. 
GUIs: 
1) Build executables with app/qtapp/qtapp.pro project file modifying defines in .pri files.
2) Install executables /usr/local/bin

CUIs:
1) Build executables with app/consapp/makefile 
2) Install executables to /usr/local/bin



LINUX CLI & GUI (except for Embarcadero GUI) using CMake (not used in my project)

1) create a build directory
 > mkdir build
 > cd build/
2) setup CMake project
 > cmake ..
3) compile CLI & GUI
 > make


LINUX: To build and install code

CUIs:
1) cd app/consapp/<appName>/gcc
2) make

GUIs (Qt based): (QTcreator community edition use and selected 5.15.2 tool chain)
1) Make sure path for qmake is in the path with .bashrc export PATH="/path/Tools/version/gcc_64/bin:$PATH"
2) cd app/qtapp
3) qmake qtapp.pro # creates makefile
4) make


