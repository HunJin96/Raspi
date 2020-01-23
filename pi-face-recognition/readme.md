## OpenCv安裝
# 
### 第一步 擴展文件系統並回收空間
#
* sudo raspi-config
#### 然後選擇"7個高級選項"菜單項：
![raspi](https://www.pyimagesearch.com/wp-content/uploads/2019/09/install_opencv4_buster_raspi_config.jpg)
#### 然後選擇"A1擴展文件系統"：
![A1擴展文件系統](https://www.pyimagesearch.com/wp-content/uploads/2019/09/install_opencv4_buster_raspi_config_expand_fs.jpg)
* sudo reboot
### 第二部 安裝依賴項
#
#### 更新和升級任何現有軟件包：
* sudo apt-get update && sudo apt-get upgrade
#### 我們需要安裝一些開發人員工具，包括CMake
* sudo apt-get install build-essential cmake pkg-config
#### 我們需要安裝一些映像I / O，包括JPEG，PNG，TIFF等
* sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng-dev
#### 正如我們需要圖像I / O包一樣，我們也需要視頻I / O包。這些庫使我們可以從磁盤讀取各種視頻文件格式，以及直接使用視頻流：
* sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
* sudo apt-get install libxvidcore-dev libx264-dev
#### OpenCV庫帶有一個名為highgui的子模塊，該子模塊 用於在我們的屏幕上顯示圖像並構建基本的GUI。
* sudo apt-get install libfontconfig1-dev libcairo2-dev
* sudo apt-get install libgdk-pixbuf2.0-dev libpango1.0-dev
* sudo apt-get install libgtk2.0-dev libgtk-3-dev
#### 可以進一步優化OpenCV內部的許多操作
* sudo apt-get install libatlas-base-dev gfortran
#### 它們用於HDF5數據集和Qt GUI
* sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
* sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
#### Python 3標頭文件，以便我們可以使用Python綁定編譯OpenCV
* sudo apt-get install python3-dev
### 第三部 創建Python虛擬環境並安裝NumPy
#
# 安裝pip
* wget https://bootstrap.pypa.io/get-pip.py
* sudo python get-pip.py
* sudo python3 get-pip.py
* sudo rm -rf ~/.cache/pip
#### 安裝  virtualenv   和 virtualenvwrapper
* sudo pip install virtualenv virtualenvwrapper
#### 一旦雙方 的virtualenv   和 virtualenvwrapper   均已安裝完畢，打開你的 〜/ .bashrc中   的文件：
* nano ~/.bashrc
#### 並將以下行添加到文件底部
# virtualenv and virtualenvwrapper
* export WORKON_HOME=$HOME/.virtualenvs
* export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
* source /usr/local/bin/virtualenvwrapper.sh
#### 從那裡，重新加載 〜/ .bashrc   文件，以將更改應用於當前的bash會話：
* source ~/.bashrc
#### 創建您的Python 3虛擬環境
* mkvirtualenv cv -p python3
### 第四部 安裝OpenCV 4
#
* pip install opencv-contrib-python==4.1.0.25
### 第五部 測試您的OpenCV 4 
#
#### 嘗試導入OpenCV庫
* cd ~
* workon cv
* python
* import cv2
* cv2.__version__
* '4.1.1'
#### 使用face_recognition 在樹梅派
#
#### 安裝 dlib
* workon <your env name> 
* pip install dlib
#### 安裝 face_recognition
* pip install face_recognition
#### 安裝 imutils
* pip install imutils
### DataSet Directory Structure:
![raspi](https://www.pyimagesearch.com/wp-content/uploads/2019/09/install_opencv4_buster_raspi_config.jpg)
### 訓練指令
* python encode_faces.py --dataset dataset --encodings encodings.pickle \
	--detection-method hog
### 執行指令
* python pi_face_recognition.py --cascade haarcascade_frontalface_default.xml \
	--encodings encodings.pickle
