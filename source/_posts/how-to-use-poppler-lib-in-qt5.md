---
title: How to use poppler lib in Qt 5
date: 2019-12-21 19:56:58
tags:
---


Poppler is a C++ library that is useful to load and acess PDF file into your program.

Here is how you can use it in Qt 5.

1. download from poppler.freedesktop.org

    By the time of writing this article the link is [https://poppler.freedesktop.org/poppler-0.83.0.tar.xz]()
2. build with your Qt installation path

    ```
    cmake .. -DCMAKE_PREFIX_PATH=~/Qt5.12.3/5.12.3/clang_64/lib/cmake/
    make
    ```
    
3. install the poppler libs

     ```
     make install
     ```
     
4. add poppler to your Qt project file

    ```
    INCLUDEPATH += /usr/local/include/poppler/qt5
    LIBS += -L/usr/local/lib/ -lpoppler-qt5
    ```
5. now you can `#include` it in your C++ file!

    ```
     #include <poppler-qt5.h>
    ```
6. try this lines copied from example from poppler site.
    
    ```
     Poppler::Document* document = Poppler::Document::load(fileName);
        if (!document || document->isLocked()) {
          // ... error message ....
          delete document;
          return;
        }
    
        // Paranoid safety check
        if (document == 0) {
          // ... error message ...
          return;
        }
    
        // Access page of the PDF file
        Poppler::Page* pdfPage = document->page(0);  // Document starts at page 0
        if (pdfPage == 0) {
          // ... error message ...
          return;
        }
        // Generate a QImage of the rendered page
        QImage image = pdfPage->renderToImage();
        if (image.isNull()) {
          // ... error message ...
          return;
        }
        // ... use image ...
        // this is how usually we do it with Qt
        ui->imageLabel->setPixmap(QPixmap::fromImage(image));
    
        // after the usage, the page must be deleted
        delete pdfPage;
    
        delete document;
        
    ```
    
    I hope this useful for those who might get stuck wondering how to do it.
    
    > Bye!
