#
# Copyright (C) Mellanox Technologies Ltd. 2001-2017.  ALL RIGHTS RESERVED.
# $COPYRIGHT$
#
# Additional copyrights may follow
#
# $HEADER$
#

ucx_sources = \
	osc_ucx.h \
	osc_ucx_request.h \
	osc_ucx_comm.c \
	osc_ucx_component.c \
	osc_ucx_request.c \
	osc_ucx_active_target.c \
	osc_ucx_passive_target.c

AM_CPPFLAGS = $(osc_ucx_CPPFLAGS)

# Make the output library in this directory, and name it either
# mca_<type>_<name>.la (for DSO builds) or libmca_<type>_<name>.la
# (for static builds).

if MCA_BUILD_ompi_osc_ucx_DSO
component_noinst =
component_install = mca_osc_ucx.la
else
component_noinst = libmca_osc_ucx.la
component_install =
endif

mcacomponentdir = $(pkglibdir)
mcacomponent_LTLIBRARIES = $(component_install)
mca_osc_ucx_la_SOURCES = $(ucx_sources)
mca_osc_ucx_la_LIBADD =  $(osc_ucx_LIBS)
mca_osc_ucx_la_LDFLAGS = -module -avoid-version $(osc_ucx_LDFLAGS)

noinst_LTLIBRARIES = $(component_noinst)
libmca_osc_ucx_la_SOURCES = $(ucx_sources)
libmca_osc_ucx_la_LIBADD = $(osc_ucx_LIBS)
libmca_osc_ucx_la_LDFLAGS = -module -avoid-version $(osc_ucx_LDFLAGS)
