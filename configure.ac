dnl Initialize autoconf
AC_PREREQ([2.63])
AC_INIT([GRay2], m4_esyscmd([head -c8 .version]), [chanc@email.arizona.edu], [gray])
AC_CONFIG_AUX_DIR([.build-aux])
AC_CONFIG_MACRO_DIR([.build-m4])
AC_CONFIG_SRCDIR([mod/gray.h])

dnl Initialize automake
AM_INIT_AUTOMAKE([1.11.1 -Wall -Werror gnu]) dnl cannot use gnits because of version number and the missing "THANKS" file
m4_ifdef([AM_PROG_AR], [AM_PROG_AR]) dnl AM_PROG_AR was introduced in automake-1.11.2

dnl Initialize libtool
LT_PREREQ([2.2.6b])
LT_INIT([dlopen disable-static])

dnl Check the required lux framework
AX_REQUIRE_LUX

dnl Make doxygen documentation a configure option (default disabled)
AC_ARG_ENABLE([doc], [AC_HELP_STRING([--enable-doc],[generate documentation using doxygen @<:@default=no@:>@])])
if test "x$enable_doc" = "xyes"; then
	AC_CHECK_PROG([DOXYGEN], [doxygen], [yes])
        if test "x$DOXYGEN" != "xyes"; then
		AC_MSG_ERROR([`doxygen` not found while "--enable-doc" is set; GRay2 uses doxygen to generate its documentations; either install doxygen <http://www.doxygen.org> or disable document generation])
	fi
fi
AM_CONDITIONAL([GRAY_DOC], [test "x$enable_doc" = "xyes"])

dnl Output files
AC_CONFIG_FILES(m4_esyscmd([find . -name 'Makefile.am' -type f | sed 's/\.\/\(.*\).am/\1/']))
AC_CONFIG_FILES([doc/Doxyfile])
AC_OUTPUT
