
  patch_it $SOURCE2 0 &&

  default_build &&

  if in_depends $MODULE Python ; then
    cd python && 
    python setup.py build &&
    python setup.py install
  fi
