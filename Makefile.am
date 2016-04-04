AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4
SUBDIRS = src

conffile = @PACKAGE_NAME@.sh

profiledir = $(sysconfdir)/profile.d
profile_DATA = $(conffile)

$(conffile):
	echo 'export GCONV_PATH="$(libdir)/gconv/aribb24:$${GCONV_PATH}"' > $@
