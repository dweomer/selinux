AC_PREREQ([2.69])
AC_CONFIG_MACRO_DIRS([m4])

m4_define([libselinux_VERSION], m4_normalize(m4_include([VERSION])))

AC_INIT([libselinux], m4_defn([libselinux_VERSION]), [selinux@vger.kernel.org],
        [libselinux], [https://github.com/SELinuxProject/selinux])
AC_CONFIG_SRCDIR([utils/selinuxenabled.c])
PKG_PROG_PKG_CONFIG
PKG_CHECK_MODULES([PCRE], [libpcre2-8],[CFLAGS="-DUSE_PCRE2 -DPCRE2_CODE_UNIT_WIDTH=8 $CFLAGS"],[PKG_CHECK_MODULES([PCRE], [libpcre])])
PKG_CHECK_MODULES([SEPOL], [libsepol])
LT_INIT
AM_INIT_AUTOMAKE([silent-rules])
AC_PROG_AWK
AC_PROG_CC
AC_PROG_LIBTOOL
AC_PROG_LN_S

AM_CONDITIONAL([CC_IS_CLANG], [$CC --version | head -1 | grep clang])
AM_CONDITIONAL([CC_IS_GCC], [$CC --version | head -1 | grep gcc])

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h inttypes.h limits.h memory.h netdb.h stddef.h stdint.h stdio_ext.h stdlib.h string.h strings.h sys/ioctl.h sys/mount.h sys/socket.h sys/statvfs.h sys/vfs.h syslog.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_TYPE_UID_T
AC_C_INLINE
AC_TYPE_INT32_T
AC_TYPE_MODE_T
AC_TYPE_PID_T
AC_TYPE_SIZE_T
AC_TYPE_SSIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_LSTAT_FOLLOWS_SLASHED_SYMLINK
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_FUNC_REALLOC
AC_CHECK_FUNCS([isascii memset munmap realpath socket stpcpy strcasecmp strchr strdup strerror strncasecmp strndup strrchr strstr strtol strtoul strverscmp uname])

PKG_INSTALLDIR

AC_CONFIG_FILES([Makefile
                 include/Makefile
                 src/Makefile
                 src/libselinux.pc
                 utils/Makefile])
AC_OUTPUT
