AM_CFLAGS = -D_GNU_SOURCE -I$(abs_top_srcdir)/include $(PCRE_CFLAGS) $(SEPOL_CFLAGS)
AM_LDFLAGS = -Wl,--as-needed -D_GNU_SOURCE $(PCRE_LIBS) $(SEPOL_LIBS)

MAX_STACK_SIZE=32768

if CC_IS_GCC
EXTRA_CFLAGS = -fipa-pure-const -Wlogical-op -Wpacked-bitfield-compat -Wsync-nand \
	-Wcoverage-mismatch -Wcpp -Wformat-contains-nul -Wnormalized=nfc -Wsuggest-attribute=const \
	-Wsuggest-attribute=noreturn -Wsuggest-attribute=pure -Wtrampolines -Wjump-misses-init \
	-Wno-suggest-attribute=pure -Wno-suggest-attribute=const -U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2 \
	-Wstrict-overflow=5 -fno-semantic-interposition
else
EXTRA_CFLAGS = -Wunused-command-line-argument
endif

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
	-Wno-format-nonliteral -Wframe-larger-than=$(MAX_STACK_SIZE) \
	-fstack-protector-all --param=ssp-buffer-size=4 -fexceptions \
	-fasynchronous-unwind-tables -fdiagnostics-show-option -funit-at-a-time \
	-Werror -Wno-aggregate-return -Wno-redundant-decls \
	$(EXTRA_CFLAGS)

BUILT_SOURCES	= libselinux.pc
CLEANFILES		= libselinux.pc
lib_LTLIBRARIES	= libselinux.la

libselinux_la_LDFLAGS	= -Wl,-soname,libselinux.so.1,--version-script=libselinux.map,-z,defs $(AM_LDFLAGS)
libselinux_la_SOURCES	= \
	avc.c \
	avc_internal.c \
    avc_internal.h \
    avc_sidtab.c \
    avc_sidtab.h \
    booleans.c \
    callbacks.c \
    callbacks.h \
    canonicalize_context.c \
    check_context.c \
    checkAccess.c \
    checkreqprot.c \
    compute_av.c \
    compute_create.c \
    compute_member.c \
    compute_relabel.c \
    compute_user.c \
    context.c \
    context_internal.h \
    deny_unknown.c \
    disable.c \
    enabled.c \
    exception.sh \
    fgetfilecon.c \
    file_path_suffixes.h \
    freecon.c \
    freeconary.c \
    fsetfilecon.c \
    get_context_list.c \
    get_context_list_internal.h \
    get_default_type.c \
    get_default_type_internal.h \
    get_initial_context.c \
    getenforce.c \
    getfilecon.c \
    getpeercon.c \
    init.c \
    is_customizable_type.c \
    label.c \
    label_backends_android.c \
    label_db.c \
    label_file.c \
    label_file.h \
    label_internal.h \
    label_media.c \
    label_support.c \
    label_x.c \
    lgetfilecon.c \
    libselinux.map \
    load_policy.c \
    lsetfilecon.c \
    mapping.c \
    mapping.h \
    matchmediacon.c \
    matchpathcon.c \
    policy.h \
    policyvers.c \
    procattr.c \
    query_user_context.c \
    regex.c \
    regex.h \
    reject_unknown.c \
    selinux_check_securetty_context.c \
    selinux_config.c \
    selinux_internal.h \
    selinux_netlink.h \
    selinux_restorecon.c \
    sestatus.c \
    setenforce.c \
    setexecfilecon.c \
    setfilecon.c \
    setrans_client.c \
    setrans_internal.h \
    seusers.c \
    sha1.c \
    sha1.h \
    stringrep.c \
    validatetrans.c
