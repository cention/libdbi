LIBS = -lm
AM_CPPFLAGS = -I${top_builddir}/include -I${top_srcdir}/include

lib_LTLIBRARIES = libdbi.la

libdbi_la_SOURCES = dbi_main.c dbi_result.c dbd_helper.c atoll.c asprintf.c timegm.c
libdbi_la_LIBADD = $(LIBADD_DL)
libdbi_la_LDFLAGS = -version-info @LIB_CURRENT@:@LIB_REVISION@:@LIB_AGE@ \
                    -Wl,--version-script=${srcdir}/libdbi.map -no-undefined

AM_CPPFLAGS += -DDBI_DRIVER_DIR=\"${driverdir}\"

debug:
	$(MAKE) all CFLAGS="@DEBUG@"

profile:
	$(MAKE) all CFLAGS="@PROFILE@"
