AM_CPPFLAGS = \
	-I$(top_srcdir)/include/drm \
	-I$(top_srcdir)/tegra \
	-I$(top_srcdir)

AM_CFLAGS = -Wall -Werror

noinst_LTLIBRARIES = libdrm-test.la
libdrm_test_la_LIBADD = ../../libdrm.la
libdrm_test_la_SOURCES = \
	drm-test.c \
	drm-test.h \
	drm-test-tegra.c \
	drm-test-tegra.h

LDADD = \
	../../tegra/libdrm_tegra.la \
	../../libdrm.la \
	libdrm-test.la

TESTS = \
	openclose \
	gr2d-fill

if HAVE_INSTALL_TESTS
testdir = $(libexecdir)/libdrm/tests/tegra
test_PROGRAMS = \
	$(TESTS)
else
noinst_PROGRAMS = $(TESTS)
check_PROGRAMS = $(TESTS)
endif
