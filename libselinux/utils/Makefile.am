AM_CFLAGS = -D_GNU_SOURCE -I$(abs_top_srcdir)/include $(PCRE_CFLAGS) $(SEPOL_CFLAGS)
AM_LDFLAGS = -Wl,--as-needed -D_GNU_SOURCE -lselinux -L$(top_builddir)/src $(PCRE_LIBS) $(SEPOL_LIBS)

if CC_IS_GCC
EXTRA_CFLAGS = -fipa-pure-const -Wpacked-bitfield-compat -Wsync-nand -Wcoverage-mismatch \
	-Wcpp -Wformat-contains-nul -Wnormalized=nfc -Wsuggest-attribute=const \
	-Wsuggest-attribute=noreturn -Wsuggest-attribute=pure -Wtrampolines -Wjump-misses-init \
	-Wno-suggest-attribute=pure -Wno-suggest-attribute=const
endif

MAX_STACK_SIZE=8192
AM_CFLAGS += -O -Wall -W -Wundef -Wformat-y2k -Wformat-security -Winit-self -Wmissing-include-dirs \
          -Wunused -Wunknown-pragmas -Wstrict-aliasing -Wshadow -Wpointer-arith \
          -Wbad-function-cast -Wcast-align -Wwrite-strings -Waggregate-return \
          -Wstrict-prototypes -Wold-style-definition -Wmissing-prototypes \
          -Wmissing-declarations -Wmissing-noreturn -Wmissing-format-attribute \
          -Wredundant-decls -Wnested-externs -Winline -Winvalid-pch -Wvolatile-register-var \
          -Wdisabled-optimization -Wbuiltin-macro-redefined \
          -Wattributes -Wmultichar \
          -Wdeprecated-declarations -Wdiv-by-zero -Wdouble-promotion -Wendif-labels -Wextra \
          -Wformat-extra-args -Wformat-zero-length -Wformat=2 -Wmultichar \
          -Woverflow -Wpointer-to-int-cast -Wpragmas \
          -Wno-missing-field-initializers -Wno-sign-compare \
          -Wno-format-nonliteral -Wframe-larger-than=$(MAX_STACK_SIZE) -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2 \
          -fstack-protector-all --param=ssp-buffer-size=4 -fexceptions \
          -fasynchronous-unwind-tables -fdiagnostics-show-option -funit-at-a-time \
          -Werror -Wno-aggregate-return -Wno-redundant-decls -Wstrict-overflow=5 \
          $(EXTRA_CFLAGS)

sbin_PROGRAMS = \
	avcstat \
	compute_av \
	compute_create \
	compute_member \
	compute_relabel \
	getconlist \
	getdefaultcon \
	getenforce \
	getfilecon \
	getpidcon \
	getsebool \
	getseuser \
	policyvers \
	sefcontext_compile \
	selabel_digest \
	selabel_get_digests_all_partial_matches \
	selabel_lookup \
	selabel_lookup_best_match \
	selabel_partial_match \
	selinux_check_access \
	selinux_check_securetty_context \
	selinuxenabled

#_SOURCES			= derp.c
#_DEPENDENCIES		= $(top_builddir)/src/libselinux.la

avcstat_SOURCES				= avcstat.c
compute_av_SOURCES			= compute_av.c
compute_create_SOURCES		= compute_create.c
compute_member_SOURCES		= compute_member.c
compute_relabel_SOURCES		= compute_relabel.c
getconlist_SOURCES			= getconlist.c
getdefaultcon_SOURCES		= getdefaultcon.c
getenforce_SOURCES			= getenforce.c
getfilecon_SOURCES			= getfilecon.c
getpidcon_SOURCES			= getpidcon.c
getsebool_SOURCES			= getsebool.c
getseuser_SOURCES			= getseuser.c
policyvers_SOURCES			= policyvers.c

sefcontext_compile_SOURCES	= sefcontext_compile.c
sefcontext_compile_LDFLAGS	= $(AM_LDFLAGS) \
	$(top_builddir)/src/callbacks.lo \
	$(top_builddir)/src/label.lo \
	$(top_builddir)/src/label_backends_android.lo \
	$(top_builddir)/src/label_db.lo \
	$(top_builddir)/src/label_file.lo \
	$(top_builddir)/src/label_media.lo \
	$(top_builddir)/src/label_support.lo \
	$(top_builddir)/src/label_x.lo \
	$(top_builddir)/src/matchpathcon.lo \
	$(top_builddir)/src/regex.lo \
	$(top_builddir)/src/sha1.lo

selabel_digest_SOURCES								= selabel_digest.c
selabel_get_digests_all_partial_matches_SOURCES		= selabel_get_digests_all_partial_matches.c
selabel_lookup_SOURCES								= selabel_lookup.c
selabel_lookup_best_match_SOURCES					= selabel_lookup_best_match.c
selabel_partial_match_SOURCES						= selabel_partial_match.c
selinux_check_access_SOURCES						= selinux_check_access.c
selinux_check_securetty_context_SOURCES				= selinux_check_securetty_context.c
selinuxenabled_SOURCES								= selinuxenabled.c
