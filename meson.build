import('fs')
src_dir='src'
src_files = ['lib.c']

files_to_compile = []
foreach file: src_files
  files_to_compile += src_dir/file
endforeach

option('demo', type: 'boolean', value: false)

project('guile-yaml', 'c')
libyaml = dependency('yaml', version: '0.1')
guile = dependency('guile', version: '2.2')
lib = library('guileyaml', files(files_to_compile), dependencies: [guile, libyaml])

if get_option('demo')
  executable('demo', src_dir / 'demo.c', declare_dependency: lib)
endif
