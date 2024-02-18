imgui_node_editor_src = ['crude_json.cpp',
    'crude_json.h',
    'imgui_bezier_math.h',
    #'imgui_bezier_math.inl',
    'imgui_canvas.cpp',
    'imgui_canvas.cpp',
    'imgui_canvas.h',
    'imgui_canvas.h',
    'imgui_extra_math.h',
    #'imgui_extra_math.inl',
    'imgui_node_editor_api.cpp',
    'imgui_node_editor_internal.h',
    #'imgui_node_editor_internal.inl',
    'imgui_node_editor.cpp',
    'imgui_node_editor.h']


inc_dir = include_directories('.')

imgui_node_editor_lib = static_library('imgui_node_editor_lib', include_directories : [inc_dir], 
                            sources : imgui_node_editor_src,
                            dependencies: [imgui_lib])

imgui_node_editor_dep = declare_dependency(
  include_directories: inc_dir,
  link_with: imgui_node_editor_lib,
)