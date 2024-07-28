# eurobin-msgs

A ROS2 package that contains custom messages that are utilized in the [eurobin-perception](https://github.com/eurobin-wp1/eurobin-perception) package for the euRobin challenge.

Tested on Ubuntu 20.04 LTS and ROS Humble with Python 3.8.

## Contents
- [➤ Overview](#overview)
- [➤ Message Specifications](#message-specifications)
- [➤ Installation](#installation)
- [➤ Usage](#usage)
- [➤ Directory Structure](#directory-structure)
- [➤ Dependencies](#dependencies)

## Overview

<b>eurobin_msgs</b> contains the following custom messages:
* `Object.msg`: label and pose information of an object
* `ObjectList.msg`: a list of `Object`s
* `BoundingBox.msg`: label, confiddence score, and bounding box coordinates of an object that was detected in a 2D color image
* `BoundingBox.msg`: a list of `BoundingBox`s

## Message Specifications

### `Object`:
```
std_msgs/Header header
string label
geometry_msgs/Pose pose
```

### `ObjectList`:
```
eurobin_msgs/Object[] objects
```

### `BoundingBox`:
```
uint16 xmin
uint16 xmax
uint16 ymin
uint16 ymax
string label
float32 confidence
```

### `BoundingBoxList`:
```
std_msgs/Header header
eurobin_msgs/BoundingBox[] bounding_boxes
```

## Installation

### From Source

After cloning this repository into your workspace, build using:
```
colcon build --packages-select eurobin_msgs
```

## Usage

Simply import any of the desired messages as follows:

```
from eurobin_msgs.msg import BoundingBox, BoundingBoxList
```


## Directory Structure

<details>
<summary> Package Files </summary>

```
eurobin-msgs
│
├── msg
│   ├── BoundingBoxList.msg
│   ├── BoundingBox.msg
│   ├── ObjectList.msg
│   └── Object.msg
│
├── CMakeLists.txt
├── package.xml
├── README.md
└── LICENSE
```

</details>


## Dependencies

* `std_msgs`
* `geometry_msgs`
