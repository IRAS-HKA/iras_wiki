[Back to Home](../../README.md) / [1.5 Software Guidelines](1.5-software_guidelines.md) / **ROS2 Package Structure**

<hr>

## Required (for all) 
    <package_name> 
        package.xml                 (ros2 package for c++ and/or python)    
        README.md                   (git readme) 
## C++ package
    <package_name> 
        include/<package_name>      (c++ header files) 
        src                         (c++ source files) 
        CMakeLists.txt              (c++) 
## Python package
    <package_name>  
        <package_name>              (python scripts) 
        resource/<package_name>     (python resources) 
        setup.py                    (python setup) 
        setup.cfg                   (python setup config) 
## C++ and Python package
    <package_name> 
        <package_name>              (python scripts)

        include/<package_name>      (c++ header files) 
        src                         (c++ source files) 
        CMakeLists.txt              (c++ with cmake_python)
## Optional (for all)
    <package_name> 
        LICENSE                     (license) 

        launch                      (launch files) 
        msg                         (internal messages) 
        srv                         (internal services) 
        action                      (internal actions) 

        config/config.yaml          (ros2 parameter configs) 
        dependencies                (libraries, modules or third-party source code) 
        docker/Dockerfile           (docker file) 
        data                        (data files) 
        test                        (test files)

        .gitignore                  (to exclude unwanted folders)

## Install instructions

    ros2 pkg create example_package --build-type ament_python --node-name example_node --dependencies rclpy ros_core