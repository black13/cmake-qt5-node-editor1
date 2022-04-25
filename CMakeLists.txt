#cmake -S . -B .\build -G "Visual Studio 17 2022" -A Win32 -D CMAKE_PREFIX_PATH="C:\Qt\5.15.2\_32DLL\lib\cmake"
cmake_minimum_required(VERSION 3.22)
project(path VERSION 0.0.0 LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

if(WIN32)
  set(CMAKE_WIN32_EXECUTABLE ON)
endif()

find_package(Qt5 COMPONENTS
        Core
        Widgets
    REQUIRED QUIET
)

add_executable(path
Compiler.hpp
Connection.hpp
ConnectionBlurEffect.hpp
ConnectionGeometry.hpp
ConnectionGraphicsObject.hpp
ConnectionPainter.hpp
ConnectionState.hpp
ConnectionStyle.hpp
DataModelRegistry.hpp
Export.hpp
FlowScene.hpp
FlowView.hpp
FlowViewStyle.hpp
memory.hpp
models.hpp
Node.hpp
NodeConnectionInteraction.hpp
NodeData.hpp
NodeDataModel.hpp
NodeGeometry.hpp
NodeGraphicsObject.hpp
NodePainter.hpp
NodePainterDelegate.hpp
NodeState.hpp
NodeStyle.hpp
OperatingSystem.hpp
PortType.hpp
Properties.hpp
QStringStdHash.hpp
QUuidStdHash.hpp
Serializable.hpp
Style.hpp
StyleCollection.hpp
TypeConverter.hpp
Connection.cpp
ConnectionBlurEffect.cpp
ConnectionGeometry.cpp
ConnectionGraphicsObject.cpp
ConnectionPainter.cpp
ConnectionState.cpp
ConnectionStyle.cpp
DataModelRegistry.cpp
FlowScene.cpp
FlowView.cpp
FlowViewStyle.cpp
main.cpp
models.cpp
Node.cpp
NodeConnectionInteraction.cpp
NodeDataModel.cpp
NodeGeometry.cpp
NodeGraphicsObject.cpp
NodePainter.cpp
NodeState.cpp
NodeStyle.cpp
Properties.cpp
StyleCollection.cpp
models.hpp
models.cpp
)

target_include_directories(path PRIVATE ${CMAKE_CURRENT_LIST_DIR})

target_link_libraries(path
    PRIVATE
        Qt5::Widgets
        Qt5::Gui
)
