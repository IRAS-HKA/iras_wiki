[Back to Home](../../README.md) / [1.4 Introductions](1.4-introductions.md) / **RKIM Einführungswoche**

<hr>

{- TODO: switch to english, make it more general (not only ROS and not only for RKIM) -}

# RKIM Einführungswoche

Dieses Dokument dient als Vorbereitung auf die Einführungswoche des Studiengangs Robotik und KI in der Produktion.

Die Studierenden sollen sich selbst darum kümmern, dass alle Vorraussetzungen VOR dem Start der Veranstaltungen erfüllt sind.

Während des Studiums wird in Projekten intensiv mit ROS2 gearbeitet, deswegen ist es notwendig,

dass jeder Studierende eine lauffähige Version auf seinem privatem Rechner hat.

In der Einführungswoche werden fortgeschrittene Anwendungen vermittelt.

Die Grundlagen von ROS2 sollen selbstständig mit den verfügbaren Tutorials erlernt werden.

## Betriebssystem

Es wird das Betriebssystem Ubuntu 20.04 benötigt.
(ROS2 Foxy ist auch für Windows 10 und macOS verfügbar, dafür kann aber kein Support geleistet werden)

Für die Installation gibt es verschiedene Optionen abhängig vom vorhandenen Gerät:

1. Dual Boot (empfohlen)

    <https://medium.com/linuxforeveryone/how-to-install-ubuntu-20-04-and-dual-boot-alongside-windows-10-323a85271a73>

2. Parallels (nur für Mac)

    <https://www.parallels.com/de/landingpage/pd/education/>

3. Separater Laptop mit Ubuntu Neuinstallation (falls möglich die beste Option)

## Softwarepakete

Folgende Softwarepakete sind notwendig

### ROS2 Foxy

ROS2 Foxy auf Ubuntu installieren:

<https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html>

#### Installation überprüfen

```bash
# Terminal 1
source /opt/ros/foxy/setup.bash
ros2 run demo_nodes_cpp talker
```

```bash
# Terminal 2
source /opt/ros/foxy/setup.bash
ros2 run demo_nodes_py listener
```

### Docker

Docker installieren:

<https://docs.docker.com/engine/install/ubuntu/>

Docker ohne sudo ausführen:

<https://docs.docker.com/engine/install/linux-postinstall/>

#### Installation überprüfen

```bash
docker run hello-world
```

## Tutorials


Falls bereits Vorwissen in den Themen UNIX, Python und Git vorhanden ist, können diese Tutorials übersprungen werden.

Bitte beachten Sie, dass die Bearbeitung aller Tutorials mehrere Stunden bis zu einem Tag dauern kann.

Folgende Tutorials sollen vor den Einführungsveranstaltungen bearbeitet werden:

1. UNIX Basics

    <https://www.guru99.com/must-know-linux-commands.html>

2. Python Basics

    <https://www.w3schools.com/python/python_intro.asp>  
    (Das Tutorial geht von Windows aus, es kann aber genauso mit dem vorinstallierten Python auf Ubuntu bearbeitet werden)

3. ROS2 Foxy Beginner: CLI-Tools

    <https://docs.ros.org/en/foxy/Tutorials/Beginner-CLI-Tools.html>

4. ROS2 Foxy Beginner: Client libraries (Nur Python Kapitel notwendig)

    <https://docs.ros.org/en/foxy/Tutorials/Beginner-Client-Libraries.html>

5. Git Basics

    <https://www.youtube.com/watch?v=USjZcfj8yxE>

6. Docker Basics

    <https://www.youtube.com/watch?v=eGz9DS-aIeY>

## Beispiele

Beispiele zum Strukturieren eines ROS Packages mit Docker finden Sie im internen GitLab/Common/ROS/[example_packages](https://www.w.hs-karlsruhe.de/gitlab/iras/common/ros/example_packages).
