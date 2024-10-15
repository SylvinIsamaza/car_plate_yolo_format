# Car plate yolo fomat
Car plate yolo format labels made by [labelImg](https://github.com/HumanSignal/labelImg)



## Features
- Supports annotation in PASCAL VOC and YOLO format.
- Easily create bounding boxes to label objects in an image.
- Save and load annotations for review.
- Simple and user-friendly interface

## Usage


Steps (PascalVOC)



### Steps (YOLO)


1. In ``data/predefined_classes.txt`` define the list of classes that will be used for your training.

2. Build and launch using the instructions above.

3. Right below "Save" button in the toolbar, click "PascalVOC" button to switch to YOLO format.

4. You may use Open/OpenDIR to process single or multiple images. When finished with a single image, click save.

A txt file of YOLO format will be saved in the same folder as your image with same name. A file named "classes.txt" is saved to that folder too. "classes.txt" defines the list of class names that your YOLO label refers to.

Note:

- Your label list shall not change in the middle of processing a list of images. When you save an image, classes.txt will also get updated, while previous annotations will not be updated.

- You shouldn't use "default class" function when saving to YOLO format, it will not be referred.

- When saving as YOLO format, "difficult" flag is discarded.

## Installation

### Get from PyPI but only python3.0 or above
This is the simplest (one-command) install method on modern Linux distributions such as Ubuntu and Fedora.
```bash
pip3 install labelImg
labelImg
labelImg [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
```
### Build from source
Linux/Ubuntu/Mac requires at least Python 2.6 and has been tested with PyQt 4.8. However, Python 3 or above and PyQt5 are strongly recommended.

#### Ubuntu Linux
Python 3 + Qt5
```bash
sudo apt-get install pyqt5-dev-tools
sudo pip3 install -r requirements/requirements-linux-python3.txt
make qt5py3
python3 labelImg.py
python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
```
macOS
Python 3 + Qt5
```bash
brew install qt  # Install qt-5.x.x by Homebrew
brew install libxml2

or using pip

pip3 install pyqt5 lxml # Install qt and lxml by pip

make qt5py3
python3 labelImg.py
python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
```
Python 3 Virtualenv (Recommended)

Virtualenv can avoid a lot of the QT / Python version issues
```bash
brew install python3
pip3 install pipenv
pipenv run pip install pyqt5==5.15.2 lxml
pipenv run make qt5py3
pipenv run python3 labelImg.py

[Optional] rm -rf build dist; pipenv run python setup.py py2app -A;mv "dist/labelImg.app" /Applications
```
Note: The Last command gives you a nice .app file with a new SVG Icon in your /Applications folder. You can consider using the script: build-tools/build-for-macos.sh

### Windows
Install Python, PyQt5 and install lxml.

Open cmd and go to the labelImg directory
```bash
pyrcc4 -o libs/resources.py resources.qrc
For pyqt5, pyrcc5 -o libs/resources.py resources.qrc

python labelImg.py
python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
```
If you want to package it into a separate EXE file
```bash
Install pyinstaller and execute:

pip install pyinstaller
pyinstaller --hidden-import=pyqt5 --hidden-import=lxml -F -n "labelImg" -c labelImg.py -p ./libs -p ./

```
### Windows + Anaconda
Download and install Anaconda (Python 3+)

Open the Anaconda Prompt and go to the labelImg directory
```bash
conda install pyqt=5
conda install -c anaconda lxml
pyrcc5 -o libs/resources.py resources.qrc
python labelImg.py
python labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]
Use Docker
docker run -it \
--user $(id -u) \
-e DISPLAY=unix$DISPLAY \
--workdir=$(pwd) \
--volume="/home/$USER:/home/$USER" \
--volume="/etc/group:/etc/group:ro" \
--volume="/etc/passwd:/etc/passwd:ro" \
--volume="/etc/shadow:/etc/shadow:ro" \
--volume="/etc/sudoers.d:/etc/sudoers.d:ro" \
-v /tmp/.X11-unix:/tmp/.X11-unix \
tzutalin/py2qt4

make qt4py2;./labelImg.py
```
## Getting started
1. Clone Repository
    ```
    git clone https://github.com/SylvinIsamaza/car_plate_yolo_format.git
    ```
2. Navigate to folder called  car_plate_yolo_format_label
    ```bash
    cd car_plate_yolo_format
    ```

3. You will see the following file

    | File name | Description                       |
    | :-------- | :-------------------------------- |
    | `classes.txt`  | It contain list of all classess annotated         |
    | `*.txt`  | label file for specific image        |

## Authors
- [@SylvainIsamaza](https://www.github.com/SylvinIsamaza)