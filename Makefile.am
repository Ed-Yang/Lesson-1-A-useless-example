AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4

pkglib_LTLIBRARIES = useless.la
#pkglib_LTLIBRARIES = libuseless.la
useless_la_LDFLAGS = -avoid-version -module -shared -export-dynamic

useless_la_SOURCES = e_useless.c
#libuseless_la_SOURCES = e_useless.c

# Override some variables for the examples, this is NOT necessary
pkgdatadir = /usr/share/engine-corner
pkgexecdir = /usr/share/engine-corner/libexec
pkgincludedir = /usr/share/engine-corner/include
pkglibdir = /usr/share/engine-corner/lib
