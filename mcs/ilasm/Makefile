thisdir = ilasm
SUBDIRS =
include ../build/rules.make

PROGRAM = ilasm.exe
BUILT_SOURCES = ILParser.cs
LOCAL_MCS_FLAGS = /lib:../class/lib/$(PROFILE) /r:../class/lib/$(PROFILE)/PEAPI.dll /r:Mono.CompilerServices.SymbolWriter.dll /r:Mono.Security.dll

CLEAN_FILES = parser/y.output

EXTRA_DISTFILES = \
	parser/ILParser.jay	\
	$(wildcard tests/*.il)

ILParser.cs: parser/ILParser.jay $(topdir)/jay/skeleton.cs
	$(topdir)/jay/jay -ct < $(topdir)/jay/skeleton.cs $(CURDIR)/$< >$@

include ../build/executable.make

