# Introduction #

This document tries to describe how to build all the library dependencies for gnash.

# Libs #

**GLOBAL VARIABLES**

SIMULATOR="CHANGEME" // destination path to all the libs, will be used to linking

SIMULATOR\_SDK="/Developer/Platforms/iPhoneSimulator.platform/"

SIMULATOR\_SDK\_DEVROOT="/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator3.2.sdk"

export CC="/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin/i686-apple-darwin10-gcc-4.2.1"

export CFLAGS="-I$SIMULATOR/include"

export CC="/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin/i686-apple-darwin10-gcc-4.2.1"

export CXX="/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin/i686-apple-darwin10-gcc-4.2.1"

export CFLAGS="-isysroot $SIMULATOR\_SDK\_DEVROOT -I$SIMULATOR/include -mmacosx-version-min=10.5"

export CPPFLAGS="-isysroot $SIMULATOR\_SDK\_DEVROOT -I$SIMULATOR/include -mmacosx-version-min=10.5"

export LDFLAGS="-L$SIMULATOR/lib"


## Jpeg Lib ##

./configure --prefix=$SIMULATOR --target=i686-apple-darwin10

## Gif lib ##

./configure --prefix=$SIMULATOR --target=i686-apple-darwin10

## PNG lib ##

./configure --prefix=$SIMULATOR --target=i686-apple-darwin10

## Fontconfig lib ##

./configure --prefix=$SIMULATOR --target=i686-apple-darwin10 --with-expat-includes=$SIMULATOR/include --with-expat-lib=$SIMULATOR/lib --with-freetype-config=$SIMULATOR/bin/freetype-config --disable-iconv

## FFMPEG ##

./configure --cc=$CC --as='../gas-preprocessor.pl $CC' --sysroot=SIMULATOR\_SDK\_DEVROOT --enable-cross-compile --target-os=darwin --arch=i386 --prefix=$SIMULATOR --enable-pic --disable-mmx --disable-mmx2             --disable-shared --disable-asm