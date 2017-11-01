project('glk', 'c', version : '0.6.1')

pkg = import('pkgconfig')

glk_str = 'glk-' + meson.project_version()

install_headers('glk.h', subdir : 'glk/' + glk_str)
pkg.generate(
    name :          'glk-' + meson.project_version(),
    description :   'Glk header',
    version :       meson.project_version(),
    subdirs :       'glk/' + glk_str
)

gi_dispa_lib = static_library('gi_dispa', 'gi_dispa.c', install : true, install_dir : get_option('libdir') + 'glk/' + glk_str + '/dispatch')
install_headers('gi_dispa.h', subdir : 'glk/' + glk_str + '/dispatch')
pkg.generate(
    name :          'glk_dispatch-' + meson.project_version(),
    description :   'Glk dispatch layer',
    version :       meson.project_version(),
    requires :      'glk = '+ meson.project_version(),
    subdirs :       'glk/' + glk_str + '/dispatch',
    libraries :     gi_dispa_lib
)
