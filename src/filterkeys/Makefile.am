main.c usage.c filterkeys_main.h : args.tab
	"$(CGENER)" -a ./args.tab

BUILT_SOURCES = main.c usage.c filterkeys_main.h

bin_PROGRAMS = filterkeys
filterkeys_SOURCES = filterkeys.c filterkeys.h $(BUILT_SOURCES)

TESTS_ENVIRONMENT = $(top_srcdir)/src/bin/testharness.sh
TESTS = test.conf

filterkeys_LDADD = ../libcrush/libcrush.la
CLEANFILES = $(BUILT_SOURCES)

EXTRA_DIST = args.tab test.conf test/test-filter.in \
							test/test-1.in test/test-2.in \
							test/test-3.in test/test-4.in \
							test/test_00.sh test/test_00.expected \
							test/test_01.sh test/test_01.expected \
							test/test_02.sh test/test_02.expected \
							test/test_03.sh test/test_03.expected \
							test/test_04.sh test/test_04.expected \
							test/test_05.sh test/test_05.expected


man1_MANS = filterkeys.1
filterkeys.1 : args.tab
	../bin/genman.pl args.tab > $@
