include_defs('//BUCKAROO_DEPS')

cxx_library(
  name = 'butteraugli',
  header_namespace = 'butteraugli',
  exported_headers = {
    'butteraugli.h': 'third_party/butteraugli/butteraugli/butteraugli.h',
  },
  srcs = [
    'third_party/butteraugli/butteraugli/butteraugli.cc',
  ],
  compiler_flags = [
    '-std=c++14',
  ],
)

cxx_library(
  name = 'guetzli',
  header_namespace = 'guetzli',
  exported_headers = subdir_glob([
    ('guetzli', '*.h'),
    ('guetzli', '*.inc'),
  ]),
  srcs = glob([
    'guetzli/*.cc',
  ],
  excludes = [
    'guetzli/guetzli.cc',
  ]),
  compiler_flags = [
    '-std=c++14',
  ],
  deps = [
    ':butteraugli',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'guetzli-tool',
  srcs = [
    'guetzli/guetzli.cc'
  ],
  compiler_flags = [
    '-std=c++14',
  ],
  deps = BUCKAROO_DEPS + [
    ':guetzli',
  ],
)
