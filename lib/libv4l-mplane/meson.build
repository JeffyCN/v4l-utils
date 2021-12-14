libv4l_mplane_sources = files(
    'libv4l-mplane.c',
)

libv4l_mplane_deps = [
    dep_threads,
]

libv4l_mplane_c_args = []

if have_visibility
    libv4l_mplane_c_args += ['-fvisibility=hidden']
endif

if builtin_plugins
libv4l_mplane = static_library('v4l-mplane',
                              libv4l_mplane_sources,
                              install : true,
                              install_dir : libv4l2plugindir,
                              dependencies : libv4l_mplane_deps,
                              c_args : libv4l_mplane_c_args,
                              include_directories : v4l2_utils_incdir)
else
libv4l_mplane = shared_module('v4l-mplane',
                              libv4l_mplane_sources,
                              install : true,
                              install_dir : libv4l2plugindir,
                              dependencies : libv4l_mplane_deps,
                              c_args : libv4l_mplane_c_args,
                              include_directories : v4l2_utils_incdir)
endif

dep_libv4l_mplane = declare_dependency(link_with : libv4l_mplane)
