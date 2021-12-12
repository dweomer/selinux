AC_PREREQ([2.69])
AC_CONFIG_MACRO_DIRS([m4])

m4_define([libsepol_VERSION], m4_normalize(m4_include([VERSION])))

AC_INIT([libsepol], m4_defn([libsepol_VERSION]), [selinux@vger.kernel.org],
        [libsepol], [https://github.com/SELinuxProject/selinux])
AC_CONFIG_SRCDIR([utils/chkcon.c])
PKG_PROG_PKG_CONFIG
LT_INIT
AM_INIT_AUTOMAKE([silent-rules])
AC_PROG_CC
AC_PROG_LEX
AC_PROG_LIBTOOL
AC_PROG_LN_S

# Checks for header files.
AC_CHECK_HEADERS([arpa/inet.h fcntl.h inttypes.h limits.h netinet/in.h stddef.h stdint.h stdlib.h string.h sys/param.h sys/socket.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([memmove memset stpcpy strcasecmp strchr strdup strerror strndup strrchr strstr strtol strtoull])

AC_CONFIG_FILES([Makefile
    cil/Makefile
    cil/include/Makefile
    cil/src/Makefile
    include/Makefile
    src/Makefile
    src/libsepol.map
    src/libsepol.pc
    utils/Makefile])
AC_OUTPUT
