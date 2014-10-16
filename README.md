Install Ubuntu 11.10

$ sudo apt-get update

$ sudo apt-get install build-essential


Install Android NDK

$ tar xf android-ndk32-r10b-linux-x86.tar.bz2

$ cd android-ndk-r10b/tools

$ mkdir ~/android/lib

$ ./make-standalone-toolchain.sh --platform=android-9 --install-dir=/home/kmarcus2/android/lib --ndk-dir=/home/kmarcus2/android/android-ndk-r10b

$ export PATH=$PATH:/home/kmarcus2/android/lib/bin


Configure and make

$ export LDFLAGS=-static

$ ./configure --disable-ashtech --disable-earthmate --disable-evermore --disable-fv18 --disable-garmin --disable-garmintxt --disable-geostar --disable-gpsclock --disable-ipv6 --disable-itrax --disable-libQgpsmm --disable-mtk3301 --disable-navcom --disable-ntrip --disable-oceanserver --disable-oncore --disable-rtcm104v2 --disable-rtcm104v3 --disable-superstar2 --disable-tnt --disable-tripmate --disable-tsip --disable-ubx --disable-dbus --host=arm-linux-androideabi --with-pic --disable-oldstyle --disable-ntpshm --disable-libgpsmm --enable-shared=no --disable-sirf --prefix=/home/kmarcus2/Downloads/bin/gpsd-2.95 --enable-static

$ make

$ make install


RA files changed:

configure.ac

gpsctl.c

gpsd.c

serial.c

config.guess

config.sub
