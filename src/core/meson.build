core_sources = run_command(
  'find', meson.current_source_dir(), '-name', '*.vala', '-type', 'f',
  check: true
).stdout().strip().split('\n')


core_deps = [
  dependency('glib-2.0'),
  dependency('gio-2.0'),
  dependency('gobject-2.0')
]

core_lib = static_library('minecraft-core', core_sources,
  dependencies: core_deps,
  vala_args: ['--vapi=core.vapi'],
  install: false
)

# FIXED: Declare the dependency AFTER creating the library
core_dep = declare_dependency(
  link_with: core_lib,  # Fixed: use core_lib, not core_dep
  include_directories: include_directories('.'),
  dependencies: core_deps
)