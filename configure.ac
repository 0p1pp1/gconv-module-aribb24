AC_PREREQ([2.69])
AC_INIT([gconv-module-aribb24], [0.1])

AC_CONFIG_SRCDIR([src/arib-std-b24.c])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([foreign])
LT_INIT([disable-static])

AC_MSG_CHECKING([GCONVSYSDIR])
AC_ARG_VAR([GCONVSYSDIR], [system's gconv directory (default=/usr/lib/gconv)])
AS_IF([test x"$ac_cv_env_GCONVSYSDIR_value" == x ],
      [ac_cv_env_GCONVSYSDIR_value=/usr/lib/gconv; AC_SUBST([GCONVSYSDIR], [/usr/lib/gconv])])
AC_MSG_RESULT([\"$ac_cv_env_GCONVSYSDIR_value\"])
 
# Checks for programs.
AC_PROG_CC

# Checks for libraries.
saved_ldflags=$LDFLAGS
LDFLAGS=-L${GCONVSYSDIR}
AC_CHECK_LIB([JIS], [jisx0201_to_ucs4])
AC_CHECK_LIB([JISX0213], [jisx0213_to_ucs4])
LDFLAGS=$saved_ldflags

# Checks for header files.
AC_CHECK_HEADERS([stddef.h stdint.h stdlib.h string.h sys/param.h wchar.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE
AC_TYPE_INT16_T
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_CHECK_FUNCS([memset])


AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT
