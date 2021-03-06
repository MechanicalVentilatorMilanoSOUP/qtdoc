# Generated from alarms.pro.

cmake_minimum_required(VERSION 3.14)
project(alarms LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(INSTALL_EXAMPLEDIR "examples/demos/alarms")

find_package(Qt6 COMPONENTS Core)
find_package(Qt6 COMPONENTS Gui)
find_package(Qt6 COMPONENTS Quick)

add_qt_gui_executable(alarms
    main.cpp
)
target_link_libraries(alarms PUBLIC
    Qt::Core
    Qt::Gui
    Qt::Quick
)


# Resources:
set(qml_resource_files
    "AlarmDelegate.qml"
    "AlarmDialog.qml"
    "AlarmModel.qml"
    "TumblerDelegate.qml"
    "main.qml"
    "qtquickcontrols2.conf"
)

qt6_add_resources(alarms "qml"
    PREFIX
        "/"
    FILES
        ${qml_resource_files}
)

install(TARGETS alarms
    RUNTIME DESTINATION "${INSTALL_EXAMPLEDIR}"
    BUNDLE DESTINATION "${INSTALL_EXAMPLEDIR}"
    LIBRARY DESTINATION "${INSTALL_EXAMPLEDIR}"
)
