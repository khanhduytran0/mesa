if with_android_stub
  stub_libs = []

# , 'hardware'
  foreach lib : ['backtrace', 'cutils']
    stub_libs += static_library(
      lib,
      files(lib + '_stub.cpp'),
      include_directories : inc_include,
      install : false,
    )
  endforeach

# stub_libs,
  dep_android = declare_dependency(
    link_with : [
      dependency('hardware'),
      dependency('sync'),
      dependency('nativewindow'),
    ],
  )
endif
