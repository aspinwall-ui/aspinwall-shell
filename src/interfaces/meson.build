pkgdatadir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())
submoduledir = join_paths(pkgdatadir, 'aspinwall_shell', 'interfaces')

interfaces_sources = [
  '__init__.py',
  'battery.py',
  'manager.py',
  'networkmanager.py',
  'notification.py',
  'pulseaudio.py',
  'window.py',
  'x11window.py'
]

install_data(interfaces_sources, install_dir: submoduledir)
