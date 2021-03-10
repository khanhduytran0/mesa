if with_android_stub
  stub_libs = []

  foreach lib : ['backtrace', 'cutils']
    stub_libs += static_library(
      lib,
      files(lib + '_stub.cpp'),
      include_directories : inc_include,
      install : false,
    )
  endforeach

  foreach lib : ['hardware']
    stub_libs += shared_library(
      lib,
      files(lib + '_stub.cpp'),
      include_directories : inc_include,
      install : false,
    )
  endforeach

  stub_libs += dependency('sync')
  stub_libs += dependency('nativewindow')

  dep_android = declare_dependency(
    link_with : stub_libs,
  )
endif
