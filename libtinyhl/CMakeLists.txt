set(SOURCE 
    glctxnotify.cpp
    glsl.cpp
    syntaxhighlighter.cpp
    )
set(MOC_FILES
    glctxnotify.h
    )
set(CMAKE_AUTOMOC ON)
find_package(Qt5 REQUIRED COMPONENTS Widgets OpenGL)
add_library(libtinyhl STATIC ${SOURCE} ${MOC_FILES})
target_link_libraries(libtinyhl Qt5::Widgets Qt5::OpenGL)
