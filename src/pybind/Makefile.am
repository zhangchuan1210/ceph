
if ENABLE_CLIENT
if WITH_CYTHON

PY_DISTUTILS = \
	CPPFLAGS="-iquote \${abs_srcdir}/include ${AM_CPPFLAGS} ${CPPFLAGS}" \
	CFLAGS="-iquote \${abs_srcdir}/include ${AM_CFLAGS} ${CFLAGS}" \
	LDFLAGS="-L\${abs_builddir}/.libs $(subst -pie,,${AM_LDFLAGS}) ${LDFLAGS}" \
	CYTHON_BUILD_DIR="$(shell readlink -f $(builddir))/build" \
	${PYTHON} ./setup.py

if WITH_RADOS
include pybind/rados/Makefile.am
if WITH_RBD
include pybind/rbd/Makefile.am
endif # WITH_RBD
if WITH_CEPHFS
include pybind/cephfs/Makefile.am
endif # WITH_CEPHFS
endif # WITH_RADOS

endif # WITH_CYTHON
endif # ENABLE_CLIENT
