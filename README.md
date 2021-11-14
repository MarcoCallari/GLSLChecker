GLSLChecker
===========
GLSL language syntax highlighter & compile error checker

## Screen Shots
![ScreenShot_0](/screenshots/screen_shot0.png "screen shot 0") 

syntax highlighting.

![ScreenShot_1](/screenshots/screen_shot1.png "screen shot 1")

the compiler error message is printed below.

## Build
The only dependency is the Qt library. Minimum version is 5.2, but it works with newer version as well (I personally compile it with Qt 5.15.2).
Compiling:
```bash
	$ mkdir build
	$ cd build
	$ cmake -DCMAKE_PREFIX_PATH="[QT_PATH]\5.15.2\msvc2019_64\lib\cmake" ..
	$ cmake --build .
```
The CMAKE_PREFIX_PATH variable should be changed accordingly. 

## License
MIT License

## Copyright
Copyright (c) 2014 Degarashi

