# build shared object
sedit "s@CFLAGS=@CFLAGS+=@" src/Makefile &&
CFLAGS+=" -fPIC -DLUA_COMPAT_5_2 -DLUA_COMPAT_5_1" &&
sedit "s:TO_LIB=:\0 liblua.so.${VERSION%.*}:" Makefile &&

sedit "s:/usr/local:/usr:" Makefile src/luaconf.h &&
sedit "s:/man/man1:/share/man/man1:" Makefile &&
sedit "s:lib/lua/\$V:lib:" Makefile &&
sedit "s:share/lua/\$V:share:" Makefile &&

(
cat > lua.pc <<EOF
prefix=/usr
exec_prefix=\${prefix}
libdir=\${prefix}/lib
includedir=\${prefix}/include

Name: Lua
Description: An Extensible Extension Language
Version: $VERSION
Requires:
Libs: -L\${libdir} -llua -lm
Cflags: -I\${includedir}
EOF
) &&

make linux &&
prepare_install &&
make install &&

ln -s /usr/lib/liblua.so.${VERSION%.*} /usr/lib/liblua.so &&

install -Dm0644 lua.pc /usr/lib/pkgconfig/
