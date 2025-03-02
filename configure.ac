#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.72])
AC_CONFIG_MACRO_DIRS([m4])
AC_INIT([libpafe],[0.0.9],[ZXB01226@nifty.com])
AM_INIT_AUTOMAKE

AC_CONFIG_SRCDIR([src/libpafe.h])
AC_CONFIG_SRCDIR([tests/pasori_test.c])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CC
AM_PROG_CC_C_O

LT_INIT
AC_ENABLE_SHARED
dnl AC_DISABLE_STATIC([])
# LT_INIT

AC_PROG_INSTALL
AC_PROG_MAKE_SET

# Autoupdate added the next two lines to ensure that your configure
# script's behavior did not change.  They are probably safe to remove.
AC_CHECK_INCLUDES_DEFAULT
AC_PROG_EGREP

AC_CHECK_HEADERS([fcntl.h stdlib.h stdio.h string.h sys/ioctl.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_CHECK_HEADERS_ONCE([sys/time.h])

AC_STRUCT_TM

AC_CHECK_SIZEOF(short, 2)

AC_FUNC_MALLOC
AC_FUNC_MKTIME
AC_FUNC_SELECT_ARGTYPES
AC_CHECK_FUNCS([select])

# Test for libusb
CHECK_LIBUSB_0="false"
PKG_CHECK_MODULES(LIBUSB, libusb-1.0 >= 1.0.8, AC_DEFINE([HAVE_LIBUSB_1], 1, [have libusb version 1.0]), CHECK_LIBUSB_0="true")
if [ "$CHECK_LIBUSB_0" == "true" ]
then
  PKG_CHECK_MODULES(LIBUSB, libusb >= 0.1.12, AC_DEFINE([HAVE_LIBUSB], 1, [have libusb version 0.1]))
fi

#AM_CONFIG_HEADER(config.h)
AC_CONFIG_FILES([Makefile src/Makefile tests/Makefile debian/Makefile spec/Makefile])
AC_OUTPUT
