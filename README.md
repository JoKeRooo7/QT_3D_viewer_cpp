## QT 3D viewer

Implemented in order to study the QT framework, pattern design, reading 3D objects from a file, rendering in OpenGL.

The 3D viewer implements an application data separation scheme - [MVC](https://developer.mozilla.org/en-US/docs/Glossary/MVC )

Implemented only for linux and macOS systems.

The norms of [Google style c++] have been observed(https://google.github.io/styleguide/cppguide.html )

## view

Implemented by [Marcus](https://github.com/MarkLitinskiy )

It is represented by inherited classes from the `QT` libraries for processing button signals and displaying information and QOpenGLWidget for displaying an object


## model

The model is represented by various files, the main of which is - `model.cc `. This file is needed to pull polygons with vertices from the file and link between all other files.

The reading model from the file is broken according to the [facade] pattern(https://refactoring.guru/ru/design-patterns/facade )

`model_afine_transfer.cc ` - is divided into files, where inside itself, it uses the [strategy] pattern to rotate objects in space(#https://refactoring.guru/ru/design-patterns/strategy )


## controller

Implemented as a class `calculator_controller.cc `, according to the pattern [singleton](https://ru.wikipedia.org/wiki/%D0%9E%D0%B4%D0%B8%D0%BD%D0%BE%D1%87%D0%BA%D0%B0_(%D1%88%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD_%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)).  It is needed to link the code between the view and the model, it also catches exceptions from `polish_notation.cc `. 


## Assembly

The assembly is carried out using the `Makefile`, it is enough to be in this directory and write `make install` in the terminal, it will create a folder `build` and it will contain an application ready to run.
