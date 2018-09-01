# A useless example

This is an example of the absolute minimum needed to create an OpenSSL
engine using autoconf, automake and libtool

## Build

Build as follows:

    $ autoreconf -i
    $ ./configure
    $ make

A quick and easy test goes like this:

    $ OPENSSL_ENGINES=.libs openssl engine -t -c useless

Considering this engine has no futher use, we'll stop here.

---

## OpenSSL 1.1.x

It seems the name of dynamic library "libuseless" is also used as engine id, so we have to change the name of dynamic library to "useless".

### Linux

```Bash
export OPENSSL_ROOT_DIR=<openssl-install-dirrectory>
autoreconf -i
./configure --with-openssl=$OPENSSL_ROOT_DIR
make
OPENSSL_ENGINES=.libs $OPENSSL_ROOT_DIR/bin/openssl engine -c -t useless
```

### macOS

I don't know how to change the library's extension name to ".dylib", so ...

```Bash
export OPENSSL_ROOT_DIR=<openssl-install-dirrectory>
autoreconf -i
./configure --with-openssl=$OPENSSL_ROOT_DIR
make
ln -s .libs/useless.so .libs/useless.dylib
OPENSSL_ENGINES=.libs $OPENSSL_ROOT_DIR/bin/openssl engine -c -t useless
```
