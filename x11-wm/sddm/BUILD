  sedit "4d" services/sddm.service.in &&
  sedit "s: getty@tty1.service plymouth-quit.service::" services/sddm.service.in &&

  mkdir -p /var/lib/sddm &&

  add_priv_group sddm &&
  add_priv_user sddm -d /var/lib/sddm -g sddm sddm &&

  OPTS+=" -DDBUS_CONFIG_FILENAME=org.freedesktop.sddm.conf" &&

  default_cmake_build

  chown -R sddm:sddm /var/lib/sddm > /dev/null &&

# Tweak some PAM stuff
  sedit "s:system-login:system-auth:g" /etc/pam.d/sddm &&
  sedit "s:system-local-login:system-auth:g" /etc/pam.d/sddm-autologin &&
  sedit "s:session         optional pam_systemd.so:-session         optional pam_systemd.so:" /etc/pam.d/sddm-greeter
