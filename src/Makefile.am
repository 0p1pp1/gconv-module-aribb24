gconv_ldflags = -shared -module -avoid-version --version-script=gconv.map

gconvexecdir = $(libdir)/gconv/aribb24
gconvexec_LTLIBRARIES = ARIB-STD-B24.la
dist_gconvexec_DATA = gconv-modules

gconv_base_sources = iconv/skeleton.c iconv/loop.c
arib-std-b24.c: $(gconv_base_sources)

ARIB_STD_B24_la_SOURCES = arib-std-b24.c jis0201.h jis0208.h jisx0213.h
ARIB_STD_B24_la_LDFLAGS = $(gconv_ldflags) -L$(GCONVSYSDIR) -R $(GCONVSYSDIR) -lJIS -lJISX0213

EXTRA_ARIB_STD_B24_la_DEPENDENCIES = gconv.map

EXTRA_DIST = gconv.map $(gconv_base_sources)
