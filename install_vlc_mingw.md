```bat
$sudo apt-get install gcc-mingw-w64-i686 g++-mingw-w64 mingw-w64 mingw-w64-tools
```

http://ftp.debian.org/debian/pool/main/m/mingw-w64/

wget http://ftp.debian.org/debian/pool/main/m/mingw-w64/mingw-w64-i686-dev_4.0.4-1_all.deb

```bat
$sudo dpkg -i mingw-w64-i686-dev_4.0.4-1_all.deb
```

### 3rd library
```bat
$sudo apt-get build-dep vlc
$sudo apt-get install git lua5.1 libtool automake autoconf make gettext pkg-config qt4-dev-tools subversion cmake cvs zip p7zip nsis bzip2 p7zip-full
```

### Get the source code
```
$ git clone git://git.videolan.org/vlc.git vlc
$ cd vlc
$ mkdir -p contrib/win32
$ cd contrib/win32
$ ../bootstrap --host=i686-w64-mingw32
$ make prebuilt
$ cd -
$ ./bootstrap 
$ mkdir -p win32 && cd win32
$ export PKG_CONFIG_LIBDIR=/home/ubuntu/Works/tools/vlc/contrib/i686-w64-mingw32/lib/pkgconfig

$ ../extras/package/win32/configure.sh --host=i686-w64-mingw32  
$ make
$ make package-win-common
```


Q. error: libgcrypt version 1.1.94 or higher not found

A. --disable-update-check
