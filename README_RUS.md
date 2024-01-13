## QT 3D viewer

Реализован с целью изучения фреймворка QT, паттерной проектирования, считывания 3D объектов из файла, отрисовки в OpenGL.

В 3D viewer реализована схема разделения данных приложения - [MVC](https://developer.mozilla.org/en-US/docs/Glossary/MVC)

Реализован только для linux и macOS систем.

Соблюдены нормы [Google style c++](https://google.github.io/styleguide/cppguide.html)

## view

Реализован [Marcus](https://github.com/MarkLitinskiy)

Представлен наследуемыми классами из библиотек `QT` для обработки сигналов с кнопок и отображения информации и QOpenGLWidget для отображения объекта


## model

Модель представлена различными файлами, основным из которых является - `model.cc`. Этот файл нужнн для стягивания из файла полигонов с вершинами и связи между всеми остальными файлами.

Модель считвания из файла разбит, согласно паттерну [фасад](https://refactoring.guru/ru/design-patterns/facade)

`model_afine_transfer.cc` - разбит на файлы, где внутри себя, для поворотов объектов в пространстве использует паттерн [стратегия](#https://refactoring.guru/ru/design-patterns/strategy)


## controller

Реализован в виде класса `calculator_controller.cc`, согласно паттерну [singleton](https://ru.wikipedia.org/wiki/%D0%9E%D0%B4%D0%B8%D0%BD%D0%BE%D1%87%D0%BA%D0%B0_(%D1%88%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD_%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)).  Нужен для связи кода между view и model, также отлавливает исключения из `polish_notation.cc`. 


## Cборка

Сборка осуществляется с помощью `Makefile`, достоаточно находиться в данной директории и написать `make install` в терминале, он создаст папку `build` и в ней будет находиться готовое для запуска приложение.
