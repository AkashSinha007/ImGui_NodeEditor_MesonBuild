example_sources = 'basicnode.cpp'

#imgui_node_editor_lib = dependency('imgui_node_editor_lib')

executable('mynode', example_sources,
           dependencies: [imgui_lib,glfw_lib,gl, imgui_node_editor_dep,application_dep])


#Copy the resource files to build directory so that font files can be loaded
src = join_paths(meson.source_root(), 'src/dependency/data')
dest = join_paths(meson.build_root(), 'src/app/data')
message('copying @0@ to @1@ ...'.format(src, dest))
# run_command('cp','-r', src, dest)

copy_command = ['cp', '-r', src, dest]

result = run_command(copy_command, check: true)
if result.returncode() != 0
    error('Failed to copy files: @0@'.format(result.stderr()))
endif