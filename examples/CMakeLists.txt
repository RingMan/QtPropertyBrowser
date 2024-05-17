
INCLUDE_DIRECTORIES(
  ${${PROJECT_NAME}_SOURCE_DIR}/src
  )

# setting a common place to put all executable files
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

ADD_SUBDIRECTORY(canvas_typed)
ADD_SUBDIRECTORY(canvas_variant)
ADD_SUBDIRECTORY(decoration)
ADD_SUBDIRECTORY(demo)
ADD_SUBDIRECTORY(extension)
ADD_SUBDIRECTORY(object_controller)
ADD_SUBDIRECTORY(simple)
ADD_SUBDIRECTORY(json)

set_target_properties(
  canvas_typed canvas_variant decoration demo extension object_controller simple json PROPERTIES
  VS_DEBUGGER_ENVIRONMENT "PATH=${Qt5BinDir}"
  VS_DEBUGGER_WORKING_DIRECTORY ${CMAKE_BINARY_DIR}/Debug
  RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/Debug
  RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/Release)
