AM_LDFLAGS = -no-undefined -export-symbols-regex '^lux[A-Z_].*' -export-dynamic -module -release 2

jobdir = $(libdir)/lux/job
job_LTLIBRARIES = gray.la

gray_la_CPPFLAGS = -DLUX_MOD_NAME=gray
gray_la_SOURCES  = gray.h gray.c
gray_la_LIBADD   = -lux

install-exec-hook:
	mkdir -p $(DESTDIR)$(bindir) && cd $(DESTDIR)$(bindir) && ln -sf lux gray

uninstall-hook:
	rm -f $(DESTDIR)$(bindir)/gray
