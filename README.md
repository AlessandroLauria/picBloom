# picBloom v1.0.1
picBloom is a cross-platform desktop app focused on the image processing. It implements operations described below:
- Color Change:
  - Brightness
  - Contrast
  - Saturation
- Blur filters:
  - Arithmetic mean
  - Geometrich mean
  - Harmonic mean
  - Median
- Edge detection:
  - Canny
  - DroG
- SRM
- Transformation:
  - Translate x-y
  - Scaling
  - Rotation

# Installation on OsX
To install the final application on Mac OsX you have to download the .app file from the following link:
http://picbloom.altervista.org/home/index.html#about

After that, place the .app in your Application folder and double click on it

# Installation on Windows
To install the final application on Windows you have to download the .exe file from the following link:
http://picbloom.altervista.org/home/index.html#about

# Installation on Linux
To install the final application on Linux dist you have to download the .sh file from the following link:
http://picbloom.altervista.org/home/index.html#about

# To contribute
Clone the repository and work in your OS folder. 

To run the code you have to lunch the following command, by command line:
- python picBloom.py

If everything go right the main window will open, if not, install the dependecies required:
- pip install pillow
- pip install pyqt5
- pip install opencv-python
- pip install imutils

# Software structure
The software is splitted in many files. The task of these is described below:
- picBloom.py:
   This is the main window that handle the grafic intefarce of the application. Launch this file with python (or python3) to start the application.
- Filters.py:
   A library that implements all filters used by the application. If you want to add one new filter you need to update this file and use the new filter in picBloom.py following the "work flow" for the user interface.
- MessageBox.py:
   Probabily it not need to be modified. It open a message box that allow the user to use the filters selected.
- SRM.py:
   The implementation of Statistical Region merging. This use UnionFind.py.
- UnionFind.py:
   Implementation of Union Find.
- ImportFile.py
   Show the 'import window' to allow the user to choose the image.
  
All images (like icons) used by the application are placed in the 'Images' folder.

# Make the Bundle (OsX,Windows,Linux)

I used pyinstaller to make the executable. It is a cross-platform software that provide an auto detection of dependecy and make the bundled app.

In the picBloom.spec file are defined the basic parameters for the export.

Use this command to make the bundle:
- pip install pyinstaller (only one time to install pyinstaller)
- pyinstaller picBloom.spec --windowed

### Bug on OsX version of pyinstaller
Using OsX I found a bug of pyinstaller that make a wrong import of cv2 and imutils libraries. To make it work is necessary press right button on .app file and click on 'Show Contents'. After that go into Contents/MacOs/ and then paste there the libraries folders.

# Future Developements

- The application need of course of an implementation of more filters. 
- Some bugs have to be fixed. 
- The SRM algorithm need an improvement.
- Graphic adaptation for different OS
- Drag and Drop system

