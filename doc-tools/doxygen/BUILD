
# See; http://sources.gentoo.org/cgi-bin/viewvc.cgi/gentoo-x86/app-doc/doxygen/files/doxygen-1.8.4-libreoffice.patch
  sedit "s:FileNamespaces:FileConstantGroups:" src/layout.cpp &&

# Fix some flex versioning issues
  sedit "s:YY_FLEX_SUBMINOR_VERSION<33:YY_FLEX_MINOR_VERSION<6 \&\& YY_FLEX_SUBMINOR_VERSION<33:g" src/code.l src/fortrancode.l src/pycode.l src/vhdlcode.l src/xmlcode.l &&
  sedit "s:YY_FLEX_MINOR_VERSION>=5 \&\& YY_FLEX_SUBMINOR_VERSION>=33:YY_FLEX_MINOR_VERSION>5 \|\| YY_FLEX_MINOR_VERSION>=5 \&\& YY_FLEX_SUBMINOR_VERSION>=33:g" src/commentscan.l &&

  default_cmake_build
