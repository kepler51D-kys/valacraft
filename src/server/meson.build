server_sources = run_command(
  'find', meson.current_source_dir(), '-name', '*.vala', '-type', 'f',
  check: true
).stdout().strip().split('\n')

server_deps = [
  dependency('glib-2.0'),
  dependency('gio-2.0'),
  dependency('gio-unix-2.0')
]

executable('minecraft-server', server_sources,
  dependencies: [server_deps, core_dep],
  install: false
)