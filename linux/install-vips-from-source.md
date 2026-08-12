# Install vips from source

[Vips](https://www.libvips.org) is an image processing library.

## Installing it on Debian

1. apt update
2. apt install build-essential meson ninja-build pkg-config
3. apt install libglib2.0-dev libexpat1-dev libjpeg-dev libpng-dev libtiff-dev libwebp-dev liborc-0.4-dev
4. cd ~
5. wget https://github.com/libvips/libvips/releases/download/v8.18.5/vips-8.18.5.tar.xz
6. tar xf vips-8.18.5.tar.xz
7. cd ~/vips-8.18.5
8. meson setup build
9. meson compile -C build
10. meson install -C build
11. ldconfig
12. hash -r
13. vips --version

   
