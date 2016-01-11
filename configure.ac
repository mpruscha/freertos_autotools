

AC_INIT([freertos_avr], [0.1], [pruscha.martin@gmail.com])

AC_PREREQ([2.69])
AC_CONFIG_HEADERS([config.h])



# See if the user specified '--build=`../config.guess` --host=avr' when
# running ../configure.

AC_MSG_CHECKING([if configuring for cross compile])
if test "x${build_alias}" = "x${host_alias}"; then
	if test "x${build_alias}" = "x" ; then
		build_alias='`./config.guess`'
	fi
	AC_MSG_RESULT(no)
	AC_MSG_WARN()
	AC_MSG_WARN(AVR-LIBC must be built using an avr cross-compiler.)
	AC_MSG_WARN(Try configuring with:)
	AC_MSG_WARN("$0 --build=$build_alias --host=avr")
	AC_MSG_WARN()
	AC_MSG_ERROR(aborting configure)
else
	AC_MSG_RESULT([yes])
fi

AC_MSG_CHECKING([if target host is avr])
case "$host" in
	avr* )
		AC_MSG_RESULT([yes])
		;;
	* )
		AC_MSG_RESULT(no)
		AC_MSG_WARN()
		AC_MSG_WARN(Avr-libc must be built using an avr cross-compiler.)
		AC_MSG_WARN(Try configuring with:)
		AC_MSG_WARN("$0 --build=$build --host=avr")
		AC_MSG_WARN()
		AC_MSG_ERROR(aborting configure)
		;;
esac


AC_NO_EXECUTABLES

AM_INIT_AUTOMAKE([foreign subdir-objects])


AC_PROG_CC
AC_CHECK_TOOL(AS, as, as)
AM_PROG_AS
#AC_PROG_RANLIB
AC_CHECK_TOOL(AR, ar, ar)

# Make sure that we found the right avr cross-compiler.

case "${CC}" in
   *avr*gcc*) ;;
   *) AC_MSG_ERROR(Wrong C compiler found; check the PATH!) ;;
esac
case "${AS}" in
   *avr*as*) ;;
   *) AC_MSG_ERROR(Wrong assembler found; check the PATH!) ;;
esac
case "${AR}" in
   *avr*ar*) ;;
   *) AC_MSG_ERROR(Wrong archiver found; check the PATH!) ;;
esac
#case "${RANLIB}" in
#   *avr*ranlib*) ;;
#   *) AC_MSG_ERROR(Wrong ranlib found; check the PATH!) ;;
#esac




LT_INIT

AC_CONFIG_FILES([Makefile])

AC_OUTPUT
