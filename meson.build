project('NodeEditor', 'cpp')

glfw_dep = subproject('glfw')
imgui_dep = subproject('imgui')

glfw_lib = glfw_dep.get_variable('glfw_dep')
imgui_lib = imgui_dep.get_variable('imgui_dep')
gl = dependency('gl')

subdir('src')
