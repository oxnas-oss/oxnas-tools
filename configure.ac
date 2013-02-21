# use: autoreconf -i

AC_PREREQ(2.65)

define(PNAME,[OXNAS Tools])dnl
define(PVERS,[0.0.0])dnl
define(TNAME,[oxnas-tools])dnl

syscmd(test -e .svn)dnl
ifelse(sysval, 0,dnl
	syscmd(test -n "${PACKAGE_VERSION}")dnl
	ifelse(sysval, 0,dnl
		[define([PVERS], esyscmd([echo -n ${PACKAGE_VERSION}]))]dnl
	)dnl
)dnl

AC_INIT(PNAME,PVERS,[oxnas-tools-bug@li-pro.net],TNAME,[http://www.li-pro.de/soho:ihmnhd:start])

AC_CANONICAL_TARGET
#AC_USE_SYSTEM_EXTENSIONS

AC_CONFIG_SRCDIR([src/mkoxnasblob.sh.in])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([1.10 dist-bzip2 dist-zip])
AM_MAINTAINER_MODE

AC_PREFIX_DEFAULT("/usr/local")

# Create build informations
BUILDDATE=`LC_ALL=C date +'%b %d %C%y'`
AC_SUBST(BUILDDATE)
AC_DEFINE_UNQUOTED(BUILDDATE,"$BUILDDATE",[Build date of package])

BUILDTIME=`LC_ALL=C date +%T`
AC_SUBST(BUILDTIME)
AC_DEFINE_UNQUOTED(BUILDTIME,"$BUILDTIME",[Build date of package])

# Check system type.
AC_MSG_CHECKING([checking system type])
case "$host_os" in
linux*)
	AC_MSG_RESULT([Linux])
	AC_DEFINE_UNQUOTED(LINUX,1,[This is a Linux system])
	;;
*)
	AC_MSG_RESULT(Unrecognised OS $host_os)
	AC_DEFINE_UNQUOTED(OTHEROS,1,[Some strange OS])
	;;
esac

# Checks for programs.
#AC_PROG_CC
#AC_PROG_CPP
#AC_PROG_CXX
AC_PROG_INSTALL
AC_PROG_LN_S
#PKG_PROG_PKG_CONFIG

# Checks for libraries.
#REQUIRES_LIBANY="anylib >= 0.0-0"
#AC_SUBST(REQUIRES_LIBANY)
#PKG_CHECK_MODULES(anylib, $REQUIRES_LIBANY)

# Checks for header files.
#AC_CHECK_HEADERS([fcntl.h stdlib.h string.h sys/ioctl.h sys/time.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
#AC_HEADER_STDBOOL
#AC_HEADER_STDC

# Checks for library functions.
#AC_CHECK_FUNCS([memset strrchr strstr])

# Output configuration files.
AC_CONFIG_FILES([
        Makefile
        src/Makefile
        doc/Makefile
	doc/mkoxnasblob.1
])
AC_CONFIG_FILES([src/mkoxnasblob.sh],[chmod +x src/mkoxnasblob.sh])
AC_OUTPUT

# ==========================================================================
AS_AC_EXPAND(EXPANDED_BINDIR, "$bindir")

echo "
 ---{ $PACKAGE_NAME $VERSION }---

    host os:                    ${host_os}

    prefix:                     ${prefix}
    bindir:                     ${EXPANDED_BINDIR}
"
