[Back to Home](../../README.md) / [1.5 Software Guidelines](1.5-software_guidelines.md) / **How to Write Proper Code**

<hr>

A genearal guideline for clean code can be found [here](clean_code.md)

## Python

* All python files, scripts and variables in lower case with underscores between separate words ([snake_case](https://en.wikipedia.org/wiki/Snake_case)).
* Python classes with capital letters for every word without spaces ([PascalCase](https://en.wikipedia.org/wiki/Camel_case)).

    ```
    python_example.py
    PythonClass 
    python_variable

## C++
 * Split Code in header (.h) and source file (.cpp)
 * Include with `#include <Header.h>`
 * File names in [PascalCase](https://en.wikipedia.org/wiki/Camel_case)

    ```
    Header.h
    CppFile.cpp
    CppClass
    cpp_variable
    cpp_private_variable_

## ROS 2

* .msg/.srv/.actions files in [PascalCase](https://en.wikipedia.org/wiki/Camel_case)
    ```
    Topic.msg
    ServiceDescription.srv
    ActionDescription.srv
* Topic names in [snake_case](https://en.wikipedia.org/wiki/Snake_case) with Node name as namespace
    ```
    ros_node/topic_name
* Package names in [snake_case](https://en.wikipedia.org/wiki/Snake_case)
    ```
    ros_package
* Launch files with ending `*.launch.py`

## PLC
* Use **english** variable names!
* Mark the purpose of the variable in its name
    ```ST 
    i_button_green  // this is an input variable
    o_led_red       // this is an output variable
    ```

## GitLab

* Repositories in [snake_case](https://en.wikipedia.org/wiki/Snake_case)
