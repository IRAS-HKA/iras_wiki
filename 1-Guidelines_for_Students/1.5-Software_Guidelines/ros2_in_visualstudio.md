[Back to Home](../../README.md) / [1.5 Software Guidelines](1.5-software_guidelines.md) / **Working with ROS2 in VSCode**

<hr>


for tooltip and intellisense support:

## Python

add in .vscode/settings.json

```json
{
    "python.analysis.extraPaths": [
        "/opt/ros/foxy/lib/python3.8/site-packages/"
    ],
    "python.autoComplete.extraPaths": [
        "/opt/ros/foxy/lib/python3.8/site-packages"
    ]
}
```

## C++

add in .vscode/c_cpp_properties.json

```json
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/include/**",
                "${workspaceFolder}/../../install/cpp_core/include/**",
                "/opt/ros/foxy/include/**"
            ],
            "defines": [],
            "compilerPath": "/usr/bin/gcc",
            "cStandard": "gnu11",
            "cppStandard": "gnu++14",
            "intelliSenseMode": "gcc-x64"
        }
    ],
    "version": 4
}
```
