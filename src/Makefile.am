## Process this file with automake to produce Makefile.in

AM_CPPFLAGS = -I$(top_srcdir)/include -I$(top_builddir)/include

lib_LTLIBRARIES = libogg.la

libogg_la_SOURCES = framing.c bitwise.c
libogg_la_LDFLAGS = -no-undefined -version-info @LIB_CURRENT@:@LIB_REVISION@:@LIB_AGE@

if EXTRA_PROGRAMS
# build and run the self tests on 'make check'

noinst_PROGRAMS = test_bitwise test_framing

test_bitwise_SOURCES = bitwise.c
test_bitwise_CFLAGS = -D_V_SELFTEST

test_framing_SOURCES = framing.c
test_framing_CFLAGS = -D_V_SELFTEST

check: $(noinst_PROGRAMS)
	./test_bitwise$(EXEEXT)
	./test_framing$(EXEEXT)
endif

debug:
	$(MAKE) all CFLAGS="@DEBUG@"

profile:
	$(MAKE) all CFLAGS="@PROFILE@"
