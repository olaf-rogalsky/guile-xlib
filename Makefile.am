#
# include subdirs
#

SUBDIRS = src


#
# rule for creation of an arch pkg
#

.PHONY: arch-pkg
arch-pkg: all
	makepkg -c -f -D "$(top_srcdir)/pkg/arch"


#
# rules for clean and maintainer-clean targets
#

CLEANFILES = \
	Makefile.in \
	config.guess~ \
	config.sub~ \
	configure.ac~ \
	configure~ \
	src/*.info \
	src/Makefile.in \
	"$(top_srcdir)"/pkg/arch/guile-xlib-*.pkg.* 

clean-local:
	-rm -f $(CLEANFILES)

MAINTAINERCLEANFILES = \
	$(CLEANFILES) \
	compile \
	config.guess \
	config.sub \
	depcomp \
	install-sh \
	ltmain.sh \
	missing \
	src/texinfo.tex

maintainer-clean-local:
	-rm -f $(MAINTAINERCLEANFILES)

