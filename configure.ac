AC_PREREQ(2.52)

AC_INIT([Apertium Spanish-Mezquital Otomi], [0.1.0], [jonathan.north.washington@gmail.com], [apertium-spa-ote], [https://wiki.apertium.org/wiki/Apertium-spa-ote])
AM_INIT_AUTOMAKE
AC_PROG_AWK

PKG_CHECK_MODULES(APERTIUM, apertium >= 3.6.1)
PKG_CHECK_MODULES(LTTOOLBOX, lttoolbox >= 3.5.1)


PKG_CHECK_MODULES(HFST, hfst >= 3.15.1)

PKG_CHECK_MODULES(CG3, cg3 >= 1.3.1)
PKG_CHECK_MODULES(APERTIUM_LEX_TOOLS, apertium-lex-tools >= 0.2.3)

PKG_CHECK_MODULES(APERTIUM_SEPARABLE, apertium-separable >= 0.3.3)


PKG_CHECK_MODULES(APERTIUM_RECURSIVE, apertium-recursive >= 0.0.1)

AC_PATH_PROGS(ZCAT, [gzcat zcat], [false])
AS_IF([test x$ZCAT = xfalse], [AC_MSG_ERROR([You don't have zcat nor gzcat installed])])

m4_ifdef([AP_CHECK_LING],[],[AC_MSG_ERROR([AP_CHECK_LING not defined, is apertium.m4 in ACLOCAL_PATH? See: https://wiki.apertium.org/wiki/Installation_troubleshooting])])


AP_CHECK_LING([1], [apertium-spa])

AP_CHECK_LING([2], [apertium-ote])

PKG_CHECK_MODULES(REGTEST, apertium-regtest >= 0.0.1, [],
                  [AC_MSG_WARN([Running tests requires apertium-regtest])])

AP_MKINCLUDE

AC_OUTPUT([Makefile])
