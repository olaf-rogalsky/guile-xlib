AC_INIT([guile-xlib], [0.1])
AC_CONFIG_SRCDIR([src/xlib.c])
AM_INIT_AUTOMAKE([foreign std-options])
AC_CONFIG_MACRO_DIR([m4])

#AM_MAINTAINER_MODE

GUILE_PKG([2.0 2.2 3.0])
GUILE_PROGS
GUILE_SITE_DIR

PKG_CHECK_MODULES([GUILE], [guile-$GUILE_EFFECTIVE_VERSION])

AC_ARG_WITH(
        [guile-site-dir],
        [AS_HELP_STRING(
                [--with-guile-site-dir],
                [installation path for Guile modules (default: auto-detected)]
        )],
        [guilesitedir="$withval"],
        [guilesitedir="$GUILE_SITE"]
)


AC_PROG_CC
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
LT_INIT([disable-static])

dnl Check for X.
AC_PATH_XTRA

dnl Checks for library functions.
AC_FUNC_MEMCMP

AC_SUBST([guilesitedir])
AC_MSG_RESULT([Guile site dir: $guilesitedir])

AC_CONFIG_FILES([Makefile src/Makefile])

AC_OUTPUT
