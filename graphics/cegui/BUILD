OPTS+=" -DCEGUI_SAMPLES_USE_DIRECTFB=0" &&

# the default ExpatParser segfaults over here...
OPTS+=" -DCEGUI_OPTION_DEFAULT_XMLPARSER=LibXMLParser" &&

# this is broken with boost 1.60+
OPTS+=" -DCEGUI_BUILD_PYTHON_MODULES=0" &&

# this is ridiculous, but they load modules dynamically
# and I don't know how to remove the flag only for those few..
bad_flags -s &&

default_cmake_build
