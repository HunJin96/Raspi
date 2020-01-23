## OpenCv安裝
# 
#### 第一步 擴展文件系統並回收空間
#
#### sudo raspi-config
#### 然後選擇"7個高級選項"菜單項：
![raspi](https://www.pyimagesearch.com/wp-content/uploads/2019/09/install_opencv4_buster_raspi_config.jpg)
#### 然後選擇"A1擴展文件系統"：
![A1擴展文件系統](https://www.pyimagesearch.com/wp-content/uploads/2019/09/install_opencv4_buster_raspi_config_expand_fs.jpg)
#### sudo reboot
####第二部 安裝依賴項
#
# 更新和升級任何現有軟件包：
* sudo apt-get update && sudo apt-get upgrade
# 我們需要安裝一些開發人員工具，包括CMake
* sudo apt-get install build-essential cmake pkg-config
# 我們需要安裝一些映像I / O，包括JPEG，PNG，TIFF等
* sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng-dev
# 正如我們需要圖像I / O包一樣，我們也需要視頻I / O包。這些庫使我們可以從磁盤讀取各種視頻文件格式，以及直接使用視頻流：
* sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
* sudo apt-get install libxvidcore-dev libx264-dev
# 無線網路設定
* sudo apt-get install libfontconfig1-dev libcairo2-dev
* sudo apt-get install libgdk-pixbuf2.0-dev libpango1.0-dev
* sudo apt-get install libgtk2.0-dev libgtk-3-dev
# 可以進一步優化OpenCV內部的許多操作
* sudo apt-get install libatlas-base-dev gfortran
