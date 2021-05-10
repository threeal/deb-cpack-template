cmake_minimum_required(VERSION 3.10)

project(libsomething-dev)

add_subdirectory("folder-name")

set(CPACK_GENERATOR "DEB")
set(CPACK_DEBIAN_FILE_NAME DEB-DEFAULT)

set(CPACK_DEBIAN_PACKAGE_NAME "libsomething-dev")

set(CPACK_DEBIAN_PACKAGE_VERSION 1.0.0)
set(CPACK_DEBIAN_PACKAGE_RELEASE 1)

set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "some short description")

set(CPACK_PACKAGE_DESCRIPTION
"some very long long
long long description")

set(CPACK_DEBIAN_PACKAGE_MAINTAINER "Your Name <your@email.com>")
set(CPACK_DEBIAN_PACKAGE_HOMEPAGE "https://something.org/")

set(CPACK_DEBIAN_PACKAGE_DEPENDS "libfoo, libgoo (>= 1.2)")

# Uncomment if this package has conflict with other packages
# set(CPACK_DEBIAN_PACKAGE_CONFLICTS "libpresomething-dev")

# Uncomment if this package is replacing other packages
# set(CPACK_DEBIAN_PACKAGE_REPLACES "libpresomething-dev")

include(CPack)
