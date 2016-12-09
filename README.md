# opencv
Jeday's way

https://github.com/opencv/opencv_contrib/blob/master/modules/text/samples/textdetection.cpp

// Встановити gtk+
* Для UBUNTU apt-get install libgtk-3-dev;  
* apt-get install libqt4-dev  libqt4-xml libqt4-opengl
* pkg-config --cflags --libs opencv -  вказаний шлях до бібліотек
* g++ -ggdb `pkg-config --cflags --libs opencv` textdetection.cpp -o textdetection
// cmake -DOPENCV_EXTRA_MODULES_PATH= ../opencv_contrib/modules -D WITH_QT=ON -D WITH_GTK=ON -D WITH_OPENGL=ON ../opencv; make -j5; make install

