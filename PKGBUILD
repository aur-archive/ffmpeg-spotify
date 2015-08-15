# Maintainer: Gadget3000 <gadget3000 at msn com>
pkgname=ffmpeg-spotify
pkgver=0.5.7
pkgrel=1
pkgdesc="Legacy FFMPEG (0.5.7) for Spotify for Linux."
arch=('arm' 'armv7h' 'i686' 'x86_64')
url="http://ffmpeg.org/"
license="nonfree"
source=(http://ffmpeg.org/releases/ffmpeg-0.5.7.tar.gz)
md5sums=('79bce5b9db0d94c22b0c36e71146f97a')
depends=('alsa-lib' 'bzip2' 'faac' 'lame' 'libtheora' 'libvorbis' 'openjpeg' 'rtmpdump' 'schroedinger' 'sdl' 'speex' 'x264' 'xvidcore' 'zlib')

build() {
  cd $srcdir/ffmpeg-0.5.7
  ./configure \
      --prefix=/usr/share/ffmpeg-spotify/ \
      --enable-shared \
      --enable-gpl \
      --enable-nonfree \
      --enable-libfaac \
      --enable-libvorbis \
      --enable-swscale \
      --enable-libx264 \
      --enable-libxvid \
      --enable-libspeex \
      --enable-libschroedinger \
      --enable-libopenjpeg \
      --extra-cflags=-fPIC \
      --extra-cflags=-I/usr/include/openjpeg-1.5/
  make
}

package() {
  cd $srcdir/ffmpeg-0.5.7
  make DESTDIR=$pkgdir install
}
