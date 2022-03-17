srcdir = @srcdir@

gconv_ldflags = -shared -module -avoid-version --version-script=gconv.map

gconvexecdir = $(libdir)/gconv/aribb24
gconvexec_LTLIBRARIES = ARIB-STD-B24.la
dist_gconvexec_DATA = gconv-modules

gconv_base_sources = iconv/skeleton.c iconv/loop.c
arib-std-b24.c: $(gconv_base_sources)

JISLIBS = libJIS.so libJISX0213.so
JISLIBSSRC = $(addprefix $(srcdir)/iconv/,$(JISLIBS))

install-exec-hook:
	$(INSTALL_PROGRAM) -m 755 -t "$(DESTDIR)$(gconvexecdir)" $(JISLIBSSRC)

ARIB_STD_B24_la_CFLAGS = -DPIC -fPIC
ARIB_STD_B24_la_SOURCES = arib-std-b24.c jis0201.h jis0208.h jisx0213.h
ARIB_STD_B24_la_LDFLAGS = $(gconv_ldflags) -L$(GCONVSYSDIR) -Wl,-rpath,'$$ORIGIN' $(addprefix -l,$(patsubst lib%.so,%,$(JISLIBS)))

EXTRA_ARIB_STD_B24_la_DEPENDENCIES = gconv.map

EXTRA_DIST = gconv.map $(JISLIBSSRC) $(gconv_base_sources)
