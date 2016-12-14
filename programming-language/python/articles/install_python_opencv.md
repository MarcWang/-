Open up a terminal and update the apt-get  package manager followed by upgrading any pre-installed packages:
```sh
$ sudo apt-get update
$ sudo apt-get upgrade
```

Now we need to install our developer tools:
```sh
$ sudo apt-get install build-essential cmake git pkg-config
```

OpenCV needs to be able to load various image file formats from disk, including JPEG, PNG, TIFF, etc. In order to load these image formats from disk, we’ll need our image I/O packages:
```sh
$ sudo apt-get install libjpeg8-dev libtiff4-dev libjasper-dev libpng12-dev
```

GTK development library
```sh
$ sudo apt-get install libgtk2.0-dev
```

processing video streams and accessing individual frames
```sh
$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
```

Install libraries that are used to optimize various routines inside of OpenCV:
```sh
$ sudo apt-get install libatlas-base-dev gfortran
```
