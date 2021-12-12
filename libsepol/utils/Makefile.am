# adapted from https://github.com/SELinuxProject/selinux/blob/770905024b07e30fb60fbef8cd781ab5baa63362/libsepol/utils/Makefile.am
AM_LDFLAGS = -Wl,--as-needed

bin_PROGRAMS	= chkcon
chkcon_SOURCES	= chkcon.c
chkcon_DEPENDENCIES	= $(top_builddir)/src/libsepol.la
chkcon_CFLAGS	= -I$(abs_top_srcdir)/include
chkcon_LDFLAGS	= -lsepol -L$(top_builddir)/src
