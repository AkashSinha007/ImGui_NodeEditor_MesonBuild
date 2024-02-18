conf_data = configuration_data()

if gl.found()
    
    conf_data.set('HAVE_OPENGL', true)
endif

if glfw_lib.found()
    conf_data.set('HAVE_GLFW3', true)
endif




application_lib_src = [
    'include/application.h',
    'source/application.cpp',
    'source/entry_point.cpp',
    'source/imgui_extra_keys.h',
    #'source/config.h.in',
    'source/config.h',
    'source/setup.h',
    'source/platform.h',
    'source/platform_win32.cpp',
    'source/platform_glfw.cpp',
    'source/renderer.h',
    'source/renderer_dx11.cpp',
    'source/renderer_ogl3.cpp',

    #Only if OpenGL Found- Added by Akash based on CMake config
    'source/imgui_impl_opengl3.cpp',
    'source/imgui_impl_opengl3.h',
    'source/imgui_impl_opengl3_loader.h',


    #Only if GLFW is found- Added by Akash based on CMake config
    'source/imgui_impl_glfw.cpp',
    'source/imgui_impl_glfw.h'
]


#configure_file( input: 'source/config.h.in', output:'config.h', copy: true)

# Configure header file
# configure_file(
#     input: 'source/config.h.in',
#     output: 'config.h',
#     configuration: conf_data,
# )

mac_deps = dependency('appleframeworks', modules: ['Cocoa', 'CoreFoundation', 'IOKit'])

inc_dir = [include_directories('include'), include_directories('source')]

application_lib = static_library('application_lib', include_directories : inc_dir, 
                            sources : application_lib_src,
                            dependencies: [imgui_lib,stbimage_header_dep,scope_guard_header_dep,glfw_lib,gl,mac_deps])

application_dep = declare_dependency(
  include_directories: inc_dir,
  link_with: application_lib,
)