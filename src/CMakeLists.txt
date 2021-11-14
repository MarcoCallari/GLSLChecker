set(SOURCE
    mainwindow.cpp
    main.cpp
    )
set(UI_FILES
    mainwindow.ui
    )
set(MOC_FILES
    mainwindow.h
    )
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
find_package(Qt5 REQUIRED COMPONENTS Widgets)
add_executable(GLSLChecker ${SOURCE} ${UI_FILES} ${MOC_FILES})
target_link_libraries(GLSLChecker libtinyhl Qt5::Widgets)
target_include_directories(GLSLChecker PUBLIC ${CMAKE_SOURCE_DIR}/libtinyhl)
file(GLOB jsonfiles
    ${CMAKE_SOURCE_DIR}/defs/*.json
)
foreach(file IN LISTS jsonfiles)
    add_custom_command(
                TARGET GLSLChecker POST_BUILD
                COMMAND ${CMAKE_COMMAND} -E copy_if_different ${file} $<TARGET_FILE_DIR:GLSLChecker>)
endforeach()