noinst_LTLIBRARIES = libcil.la
libcil_la_CFLAGS = -I$(abs_top_srcdir)/cil/include
nodist_libcil_la_SOURCES = cil_lexer.c
libcil_la_SOURCES = \
	cil.c \
	cil_binary.c \
	cil_binary.h \
	cil_build_ast.c \
	cil_build_ast.h \
	cil_copy_ast.c \
	cil_copy_ast.h \
	cil_find.c \
	cil_find.h \
	cil_flavor.h \
	cil_fqn.c \
	cil_fqn.h \
	cil_internal.h \
	cil_lexer.h \
	cil_lexer.l \
	cil_list.c \
	cil_list.h \
	cil_log.c \
	cil_log.h \
	cil_mem.c \
	cil_mem.h \
	cil_parser.c \
	cil_parser.h \
	cil_policy.c \
	cil_policy.h \
	cil_post.c \
	cil_post.h \
	cil_reset_ast.c \
	cil_reset_ast.h \
	cil_resolve_ast.c \
	cil_resolve_ast.h \
	cil_stack.c \
	cil_stack.h \
	cil_strpool.c \
	cil_strpool.h \
	cil_symtab.c \
	cil_symtab.h \
	cil_tree.c \
	cil_tree.h \
	cil_verify.c \
	cil_verify.h
BUILT_SOURCES = cil_lexer.c
CLEANFILES = cil_lexer.c
cil_lexer.c: cil_lexer.l
	$(LEX) -o $@ $<
