# trailsave plugin
plugindir = $(PLUMA_PLUGINS_LIBS_DIR)

AM_CPPFLAGS = \
	-I$(top_srcdir) 				\
	$(PLUMA_CFLAGS) 				\
	$(WARN_CFLAGS)

plugin_LTLIBRARIES = libtrailsave.la

libtrailsave_la_SOURCES = \
	pluma-trail-save-plugin.h	\
	pluma-trail-save-plugin.c

libtrailsave_la_LDFLAGS = $(PLUGIN_LIBTOOL_FLAGS)
libtrailsave_la_LIBADD  = $(PLUMA_LIBS)

plugin_in_files = trailsave.plugin.desktop.in
plugin_DATA = $(plugin_in_files:.plugin.desktop.in=.plugin)

$(plugin_DATA): $(plugin_in_files)
	$(AM_V_GEN) $(MSGFMT) --keyword=Name --keyword=Description --desktop --template $< -d $(top_srcdir)/po -o $@

EXTRA_DIST = $(plugin_in_files)

CLEANFILES = $(plugin_DATA)
DISTCLEANFILES = $(plugin_DATA)


-include $(top_srcdir)/git.mk
