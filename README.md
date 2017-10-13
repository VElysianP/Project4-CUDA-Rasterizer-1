# **CUDA Rasterizer**

===============



[CLICK ME FOR INSTRUCTION OF THIS PROJECT](./INSTRUCTION.md)



**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 4**


* YAOYI BAI (pennkey: byaoyi)
* Tested on: Windows 10 Professional, i7-6700HQ  @2.60GHz 16GB, GTX 980M 8253MB (My own Dell Alienware R3)

### (TODO: Your README)

*DO NOT* leave the README to the last minute! It is a crucial part of the
project, and we will not be able to grade you without a good README.

## **1. Basic Features**
**Results:** 
box:
![enter image description here](https://lh3.googleusercontent.com/-FnAGi_1t3Qo/WeExI91Y7II/AAAAAAAABBY/WvSQn90Tm3EyfTtPoVj_rjv_38gpahIxgCLcBGAs/s0/box.jpg "box.jpg")

![enter image description here](https://lh3.googleusercontent.com/-qYOfrvIJiDg/WeExNfX99KI/AAAAAAAABBk/poJABEGVu1IIOoOEKt5nm1PGoOzcKCicACLcBGAs/s0/box.gif "box.gif")
cow:
![enter image description here](https://lh3.googleusercontent.com/-9-YVj7Q4US4/WeEtx9v3pLI/AAAAAAAABAE/_w3UBgFQkuwAy8a4KNYzNRID46VbyepbwCLcBGAs/s0/cow.jpg "cow.jpg")

![enter image description here](https://lh3.googleusercontent.com/-Zfhj3tvrP5Q/WeEt2ulKUxI/AAAAAAAABAM/RT-GalorVQoF7yYEgJ3rUsICtuJa8Qh9QCLcBGAs/s0/cow.gif "cow.gif")

duck:
![enter image description here](https://lh3.googleusercontent.com/-UWEYwgzTuXI/WeEqv9movsI/AAAAAAAAA_g/oooNc5ajyLsfT-6wVgJ0waQ9IM245paNQCLcBGAs/s0/duck.jpg "duck.jpg")

![enter image description here](https://lh3.googleusercontent.com/-LQi4GtiM-3Q/WeEtJgcYxTI/AAAAAAAAA_4/0WYwtiE7orQXN7GYvA6E52oAfeebYBNLgCLcBGAs/s0/duck.gif "duck.gif")
flower:
![enter image description here](https://lh3.googleusercontent.com/-ZDCKtIGZ6nA/WeEuYNMx8JI/AAAAAAAABAY/GWdkd552qwM861O769HgauvoELkIYC71QCLcBGAs/s0/flower.jpg "flower.jpg")

![enter image description here](https://lh3.googleusercontent.com/-ueP481WcJXA/WeEuc0KWnNI/AAAAAAAABAk/wDyoTQnTwW41lEzRrbkCFvUb9pbipOjJQCLcBGAs/s0/flower.gif "flower.gif")
triangle:

di:
![enter image description here](https://lh3.googleusercontent.com/-0cPSbY6RqTw/WeEwcpuoR5I/AAAAAAAABBI/P2aahQPYW0gEJn8BMS6BqheEB8W1zwBnwCLcBGAs/s0/di.jpg "di.jpg")

![enter image description here](https://lh3.googleusercontent.com/-CB00VlVO33Y/WeEwhc6Y-_I/AAAAAAAABBQ/jACIpRS_Kc0LWdMbkYo46civzuZW9aZ6ACLcBGAs/s0/di.gif "di.gif")

CesiumMilkTruck:

2_cylinder_engine: (this one does not work smoothly)

checkerboard:


## **2. Extra Features**

### 1. Shared Memory Feature (1.0)

### 2. Additional Primitive: Lines (0.5)

Have to remap the triangle version of data we have read from gltf file into Line mode.

### 3. Additional Primitive: Points (0.5)

Have to remap the triangle version of data we have read from gltf file into Point mode, which means:
*number of vertices = number of primitives *
*number of vertices = number of indices *

## **3. Performance Analysis**

**Bottleneck of performance:**


*Improvement*: Using shared memory to perform.

The comparison between using global memory and shared memory.


### Credits

* [tinygltfloader](https://github.com/syoyo/tinygltfloader) by [@soyoyo](https://github.com/syoyo)

* [glTF Sample Models](https://github.com/KhronosGroup/glTF/blob/master/sampleModels/README.md)

