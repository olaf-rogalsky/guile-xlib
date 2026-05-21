## Process this file with Automake to create Makefile.in

ACLOCAL_AMFLAGS = -I m4
AUTOMAKE_OPTIONS = foreign

#
# Generated sources
#

BUILT_SOURCES = xlib.x
CLEANFILES = *.x

#
# Library
#

lib_LTLIBRARIES = libguilexlib.la

libguilexlib_la_SOURCES = xlib.c $(BUILT_SOURCES)
libguilexlib_la_CPPFLAGS = $(GUILE_CFLAGS)
#libguilexlib_la_CFLAGS = $(GUILE_CFLAGS)
libguilexlib_la_LDFLAGS = -version-info 0:0 -no-undefined
libguilexlib_la_LIBADD = $(X_LIBS) $(X_PRE_LIBS) -lX11 $(X_EXTRA_LIBS) $(GUILE_LIBS)

#
# Scheme sources
#

scmdatadir = $(guilesitedir)/xlib
scmdata_DATA = xlib.scm

#
# Documentation
#

info_TEXINFOS = guile-xlib.texi
guile_xlib_TEXINFOS = xlib.texi

#
# Distributed extra files
#

EXTRA_DIST = $(scmdata_DATA) autogen.sh



#
# Guile snarf support
#

## We assume the user has already installed Guile.
SNARF = guile-snarf

## guile-snarf does not allow spaces in DEFS, but PACKAGE_STRING has a
## space between the package name and the package version. Snarf does
## not need these PACKAGE definitions, I therefore remove them all.
SNARF_DEFS = $$(echo '$(DEFS)' | sed -e 's/-DPACKAGE[_A-Z]*=\\"[^"]*"//g; s/"/\\"/g')

%.x: %.c
	$(SNARF) $(SNARF_DEFS) $(AM_CPPFLAGS) $(CPPFLAGS) $(GUILE_CFLAGS) $(CFLAGS) $< > $@

## Add -MG to make the .x magic work with auto-dep code.
MKDEP = gcc -M -MG $(DEFS) $(AM_CPPFLAGS) $(CPPFLAGS) $(GUILE_CFLAGS) $(CFLAGS)


