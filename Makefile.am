ACLOCAL_AMFLAGS = -I build-aux/m4

AM_CFLAGS = -DYYDEBUG=1

bin_PROGRAMS = sql

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libsqlpars.pc

# TESTS = test/unitester

# noinst_PROGRAMS = $(TESTS)
EXTRA_DIST = sql.y sql.l \
	pscan.js \
	test-ok.sh test-fail.sh \
	fail1.sql \
	fail3.sql \
	fail4.sql \
	fail5.sql \
	xfail2.sql \
	ok1.sql \
	ok2.sql \
	ok3.sql \
	ok4.sql \
	ok5.sql \
	ok6.sql \
	ok7.sql \
	ok8.sql \
	ok9.sql \
	ok10.sql

sql_SOURCES = exec.c lib.c main.c sql-parser.h yyl.h
sql_LDADD = @JANSSON_LIBS@
nodist_sql_SOURCES = sql.c sql.tab.c sql.tab.h sql.lex.h

BUILT_SOURCES = $(nodist_sql_SOURCES)
CLEANFILES = $(nodist_sql_SOURCES) sql.output

sql.tab.c sql.tab.h:   sql.y Makefile
	${BISON} -vd $<

sql.c sql.lex.h: sql.l Makefile
	${LEX} -o $@ $<

TESTS = test-ok.sh test-fail.sh

