client_sources = run_command(
  'find', meson.current_source_dir(), '-name', '*.vala', '-type', 'f',
  check: true
).stdout().strip().split('\n')

client_deps = [
  dependency('gl'),
  dependency('glfw3'),
  dependency('glib-2.0'),
  dependency('gio-2.0')
]

executable('minecraft-client', client_sources,
  dependencies: [client_deps, core_dep],
  install: false
)