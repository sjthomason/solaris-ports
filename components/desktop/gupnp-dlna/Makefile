#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2018 Jim Mason <jmason at ibinx dot com>.  All rights reserved.
#

BUILD_BITS =            64_and_32
# All components using gobject-introspection must be built with gcc as
# gobject-introspection does not produce correct results when using Studio.
COMPILER =              gcc
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		gupnp-dlna
COMPONENT_VERSION=	0.10.5
COMPONENT_PROJECT_URL=	https://wiki.gnome.org/Projects/GUPnP
COMPONENT_ARCHIVE_HASH= \
	sha256:123e368227c11d5c17fc1aa76cbdaffa345355eb51d172cd39fc74a5b468ff6a
COMPONENT_BUGDB=        gnome/libraries
COMPONENT_ANITYA_ID=	1283


# Contains a single Python script written for Python 2.x/3.x; prefer 3.4.
PYTHON=3.4
PYTHON_VERSIONS=3.4

# Hook up tests once dependencies are installed
TEST_TARGET = $(SKIP_TEST)

include $(WS_MAKE_RULES)/gnome-component.mk

CONFIGURE_OPTIONS += --disable-static
# Required for documentation.
CONFIGURE_OPTIONS += --enable-gtk-doc
# Required for other components.
CONFIGURE_OPTIONS += --enable-introspection
CONFIGURE_OPTIONS += --enable-shared
CONFIGURE_OPTIONS += --with-pic

# Ancient configure script needs regeneration.
COMPONENT_PREP_ACTION += (cd $(@D); autoreconf -fiv);

REQUIRED_PACKAGES += developer/documentation-tool/gtk-doc
REQUIRED_PACKAGES += library/desktop/gobject/gobject-introspection
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/libxml2
REQUIRED_PACKAGES += library/desktop/gssdp
REQUIRED_PACKAGES += library/desktop/gstreamer-1
REQUIRED_PACKAGES += library/desktop/gstreamer-1/gst-plugins-base
REQUIRED_PACKAGES += library/desktop/gupnp
REQUIRED_PACKAGES += runtime/python-35
