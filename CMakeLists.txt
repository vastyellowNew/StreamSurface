cmake_minimum_required(VERSION 2.8)


project(Picking)
add_executable(${PROJECT_NAME} 
					surface_renderer.cpp
					camera.cpp
					glut_backend.cpp
					lighting_technique.cpp
					math_3d.cpp
					mesh.cpp
					picking_technique.cpp
					picking_texture.cpp
					pipeline.cpp
					simple_color_technique.cpp
					ogldev_util.cpp
					technique.cpp
					
					callbacks.h
					camera.h
					engine_common.h
					glut_backend.h
					lighting_technique.h
					math_3d.h
					mesh.h
					picking_technique.h
					picking_texture.h
					pipeline.h
					render_callbacks.h
					simple_color_technique.h
					ogldev_util.h
					ogldev_types.h
					
					lighting.vs
					picking.vs
					simple_color.vs
					lighting.fs
					picking.fs
					simple_color.fs
					)

find_package(GLUT REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(Assimp REQUIRED)

message(STATUS "ImageMagick_Magick++_INCLUDE_DIR=${ImageMagick_Magick++_INCLUDE_DIR}")

include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} ${ASSIMP_INCLUDE_DIR}/assimp ${ImageMagick_Magick++_INCLUDE_DIR} ${GLEW_INCLUDE_PATH} D:/lib/ImageMagick-6.8.9/Magick++/lib D:/lib/ImageMagick-6.8.9)

target_link_libraries(${PROJECT_NAME} ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} ${ASSIMP_LIBRARY_RELEASE} ${ImageMagick_Magick++_LIBRARY} ${GLEW_LIBRARY})

