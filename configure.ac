# Process this file with autoconf to produce a configure script.
AC_INIT([pkgconfig-sys-stubs],[1.0],[Simon.Urbanek@r-project.org])
AC_CONFIG_SRCDIR([darwin/zlib.pc])

AC_CANONICAL_BUILD
AC_CANONICAL_HOST

AC_PROG_SED

AC_PREFIX_PROGRAM([pkg-config])
AC_MSG_CHECKING([prefix])
AC_MSG_RESULT([$prefix])

AC_MSG_CHECKING([for stubs matching host])

host_osname=$(echo ${host_os} | $SED -e 's/@<:@0-9.@:>@*$//')
host_osmajor=$(echo ${host_os} | $SED -e 's/@<:@.@:>@@<:@0-9.@:>@*$//')

STUBS=''
test -d ${srcdir}/${host_osname} && STUBS="$STUBS ${srcdir}/${host_osname}"
test -d ${srcdir}/${host_osname}/${host_cpu} && STUBS="$STUBS ${srcdir}/${host_osname}/${host_cpu}"
test -d ${srcdir}/${host_osmajor} && STUBS="$STUBS ${srcdir}/${host_osmajor}"
test -d ${srcdir}/${host_osmajor}/${host_cpu} && STUBS="$STUBS ${srcdir}/${host_osmajor}/{host_cpu}"

AC_MSG_RESULT([$STUBS])
AC_SUBST([STUBS])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
