cmake_minimum_required(VERSION 3.3)
project(polygonal_map_msgs)

set(CMAKE_CXX_STANDARD 14)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

set(msg_files
  "msg/LineMap.msg"
  "msg/LineSegment.msg"
  "msg/PolygonalMap.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs geometry_msgs
)

ament_export_dependencies(std_msgs geometry_msgs)

ament_package()