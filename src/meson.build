pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())
submoduledir = join_paths(pkgdatadir, 'aspinwall_shell')

gnome = import('gnome')

gnome.compile_resources('org.dithernet.aspinwall.shell',
  'org.dithernet.aspinwall.shell.gresource.xml',
  gresource_bundle: true,
  install: true,
  install_dir: pkgdatadir,
)

python = import('python')

conf = configuration_data()
conf.set('PYTHON', python.find_installation('python3').path())
conf.set('VERSION', meson.project_version())
conf.set('localedir', join_paths(get_option('prefix'), get_option('localedir')))
conf.set('pkgdatadir', pkgdatadir)

configure_file(
  input: 'aspinwall-shell.in',
  output: 'aspinwall-shell',
  configuration: conf,
  install: true,
  install_dir: get_option('bindir')
)

utils_sources = [
  '__init__.py',
  'clock.py',
  'config.py',
  'control_panel.py',
  'panel.py',
  'notificationbox.py',
  'notification_popup.py',
  'surface.py',
  'shellmanager.py',
  'window_switcher.py'
]

install_data(utils_sources, install_dir: submoduledir)

subdir('interfaces')
subdir('ui')
subdir('stylesheet')
