add_priv_group colord &&
add_priv_user colord -d /var/run/colord -g colord &&

OPTS+=" --sysconfdir=/etc/$MODULE \
        --with-daemon-user=colord \
        --disable-systemd-login   \
        --enable-libcolordcompat  \
        --disable-argyllcms-sensor" &&

default_build
