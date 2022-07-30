pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())

install_data('org.dithernet.aspinwall.shell.gschema.xml',
  install_dir: join_paths(get_option('datadir'), 'glib-2.0/schemas')
)

compile_schemas = find_program('glib-compile-schemas', required: false)
if compile_schemas.found()
  test('Validate schema file', compile_schemas,
    args: ['--strict', '--dry-run', meson.current_source_dir()]
  )
endif

conf = configuration_data()
conf.set('VERSION', meson.project_version())
conf.set('pkgdatadir', pkgdatadir)

configure_file(
  input: 'start-aspinwall.in',
  output: 'start-aspinwall',
  configuration: conf,
  install: true,
  install_dir: get_option('bindir')
)

subdir('x11')
