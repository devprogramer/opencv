# opencv
Jeday's way

https://github.com/opencv/opencv_contrib/blob/master/modules/text/samples/textdetection.cpp

// Встановити gtk+
* Для UBUNTU apt-get install libgtk-3-dev;  
* apt-get install libqt4-dev  libqt4-xml libqt4-opengl
* pkg-config --cflags --libs opencv -  вказаний шлях до бібліотек
* g++ -ggdb `pkg-config --cflags --libs opencv` textdetection.cpp -o textdetection
* cmake -DOPENCV_EXTRA_MODULES_PATH= ../opencv_contrib/modules -D WITH_QT=ON -D WITH_GTK=ON -D WITH_OPENGL=ON ../opencv; make -j5; make install


* компіляція коду: 
* g++  textdetection.cpp -o textdetection -I/usr/local/include -L/usr/local/lib -lopencv_core -lopencv_highgui -lopencv_imgproc


>. download leptonica 1.70 tarball (helper image processing library, used by tesseract. Later versions might work too):
>http://www.leptonica.com/download.html
>unpack and build it:
>
>cd leptonica-1.70
>mkdir build && cd build && ../configure && make && sudo make install
>
>leptonica will be installed to /usr/local.
>
>2. download tesseract-3.03-rc1 tarball from https://drive.google.com/folderview?id=0B7l10Bj_LprhQnpSRkpGMGV2eE0&usp=sharing
>unpack and build it:
>
># needed only to build tesseract
>export LIBLEPT_HEADERSDIR=/usr/local/include/
>cd tesseract-3.03
>mkdir build && cd build
>../configure --with-extra-includes=/usr/local --with-extra-libraries=/usr/local
>make && sudo make install
>
>tessract will be installed to /usr/local.


* g++  textdetection.cpp -o textdetection -I/usr/local/include -L/usr/local/lib -lopencv_core -lopencv_highgui -lopencv_imgproc -lopencv_text -lopencv_imgcodecs

# Помилка
* error while loading shared libraries: libopencv_core.so.3.1: cannot open shared object file: No such file or directory
# Рішення
* export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib; ./textdetection image1.jpg
