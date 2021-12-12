AM_LDFLAGS			= -Wl,--as-needed
BUILT_SOURCES		= libsepol.map libsepol.pc
CLEANFILES			= libsepol.map libsepol.pc
lib_LTLIBRARIES		= libsepol.la
libsepol_la_CFLAGS	= -I$(abs_top_srcdir)/include -I$(abs_top_srcdir)/cil/include
libsepol_la_LDFLAGS	= -Wl,-soname,libsepol.so.1,--version-script=libsepol.map,-z,defs
libsepol_la_SOURCES	= \
	assertion.c \
	avrule_block.c \
	avtab.c \
	boolean_internal.h \
	boolean_record.c \
	booleans.c \
	conditional.c \
	constraint.c \
	context.c \
	context.h \
	context_internal.h \
	context_record.c \
	debug.c \
	debug.h \
	deprecated_funcs.c \
	ebitmap.c \
	expand.c \
	flask.h \
	handle.c \
	handle.h \
	hashtab.c \
	hierarchy.c \
	ibendport_internal.h \
	ibendport_record.c \
	ibendports.c \
	ibpkey_internal.h \
	ibpkey_record.c \
	ibpkeys.c \
	iface_internal.h \
	iface_record.c \
	interfaces.c \
	kernel_to_cil.c \
	kernel_to_common.c \
	kernel_to_common.h \
	kernel_to_conf.c \
	link.c \
	mls.c \
    mls.h \
    module.c \
    module_internal.h \
    module_to_cil.c \
    node_internal.h \
    node_record.c \
    nodes.c \
    optimize.c \
    polcaps.c \
    policydb.c \
    policydb_convert.c \
    policydb_internal.h \
    policydb_public.c \
    port_internal.h \
    port_record.c \
    ports.c \
    private.h \
    roles.c \
    services.c \
    sidtab.c \
    symtab.c \
    user_internal.h \
    user_record.c \
    users.c \
    util.c \
    write.c
