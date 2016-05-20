AC_INIT([tpm2.0-tools], [1.0.0])
AC_CONFIG_MACRO_DIR([m4])
AC_PROG_CC
AC_PROG_CXX
LT_INIT
AM_INIT_AUTOMAKE([foreign
                  subdir-objects])
AC_CONFIG_FILES([Makefile])
PKG_CHECK_MODULES([TSS2], [tss2])
PKG_CHECK_MODULES([TCTI_SOCKET], [tcti_socket])
AC_CHECK_HEADER([openssl/sha.h],
                [
                 AC_DEFINE([HAVE_OPENSSL_H],
                           [1],
                           [Define if sha.h exists.])
                 ],
                [AC_MSG_ERROR([Missing OPENSSL headers.])])
AC_CHECK_HEADER([curl/curl.h],
                [
                 AC_DEFINE([HAVE_CURL_H],
                           [1],
                           [Define if curl.h exists.])
                 ],
                [AC_MSG_ERROR([Missing CURL headers.])])
AC_CHECK_LIB([crypto], [SHA256_Init], [],
             [AC_MSG_ERROR([Missing CRYPTO library.])], [])
AC_CHECK_LIB([curl], [curl_easy_init], [],
             [AC_MSG_ERROR([Missing CURL library.])], [])
AC_OUTPUT
