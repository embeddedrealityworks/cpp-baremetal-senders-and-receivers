project(
  'baremetal-async',
  'cpp',
  version: '0.1.0',
  license: 'MIT',
  meson_version: '>=1.1.0',
  default_options: ['cpp_std=c++23']
)

mp11_sub = subproject('mp11')
mp11_dep = mp11_sub.get_variable('mp11_dep')
concurency_sub = subproject('cpp-baremetal-concurrency', default_options: ['simulate_freestanding=true'])
concurrency_dep = concurency_sub.get_variable('concurrency_dep')
stdx_sub = subproject('cpp-std-extensions')
stdx_dep = stdx_sub.get_variable('stdx_dep')

async_dep = declare_dependency(
  include_directories: include_directories('include'),
  dependencies: [mp11_dep, concurrency_dep, stdx_dep]
)
