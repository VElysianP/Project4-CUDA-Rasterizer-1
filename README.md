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
 1. Vertex shading
 2. Primitive assembly with support for triangles read from buffers of index and vertex data
 3. Rasterization
 4. Fragment shading
 5. A depth buffer for storing and depth testing fragments
 6. Fragment-to-depth-buffer writing
 7. Lambert lighting

**Results:** 
**box:**

![box normal rasterization](https://lh3.googleusercontent.com/-qYOfrvIJiDg/WeExNfX99KI/AAAAAAAABBk/poJABEGVu1IIOoOEKt5nm1PGoOzcKCicACLcBGAs/s0/box.gif "box.gif")

**cow:**

![cow normal rasterization](https://lh3.googleusercontent.com/-Zfhj3tvrP5Q/WeEt2ulKUxI/AAAAAAAABAM/RT-GalorVQoF7yYEgJ3rUsICtuJa8Qh9QCLcBGAs/s0/cow.gif "cow.gif")

**duck:**

![duck normal rasterization](https://lh3.googleusercontent.com/-LQi4GtiM-3Q/WeEtJgcYxTI/AAAAAAAAA_4/0WYwtiE7orQXN7GYvA6E52oAfeebYBNLgCLcBGAs/s0/duck.gif "duck.gif")

**flower:**

![flower normal rasterization](https://lh3.googleusercontent.com/-ueP481WcJXA/WeEuc0KWnNI/AAAAAAAABAk/wDyoTQnTwW41lEzRrbkCFvUb9pbipOjJQCLcBGAs/s0/flower.gif "flower.gif")

**triangle:**

![triangle normal rasterization](https://lh3.googleusercontent.com/-82OQF5cBjeA/WeEyKTi15YI/AAAAAAAABCM/FEzOwcA1iHgrAcdaua1ic-sIc6QKLMNpgCLcBGAs/s0/triangle.gif "triangle.gif")

**di:**

![di normal rasterization](https://lh3.googleusercontent.com/-CB00VlVO33Y/WeEwhc6Y-_I/AAAAAAAABBQ/jACIpRS_Kc0LWdMbkYo46civzuZW9aZ6ACLcBGAs/s0/di.gif "di.gif")

**CesiumMilkTruck:**

![CesiumMilkTruck normal rasterization](https://lh3.googleusercontent.com/-kzu5CXH28YU/WeEyvsZmZkI/AAAAAAAABCs/5oce21ZkNo4YZ4vUqQNOw-Sr1UtlxRA8gCLcBGAs/s0/CesiumMilkTruck.gif "CesiumMilkTruck.gif")

**2_cylinder_engine:** 

![2_cylinder_engine normal rasterization](https://lh3.googleusercontent.com/-_ls1SibOQ_E/WeEzmWnS1wI/AAAAAAAABDU/DP09VJdvFQMXjFCjVZu43MSmEo1n2tW_ACLcBGAs/s0/2_cylinder_engine.gif "2_cylinder_engine.gif")

**checkerboard:**

![checkerboard normal rasterization](https://lh3.googleusercontent.com/-zfa94tv0Wxc/WeE0O-9s1pI/AAAAAAAABDs/bEdQD3tONOYJo8uJbbVO5_zHDpGR-6NrQCLcBGAs/s0/checkerboard.gif "checkerboard.gif")

## **2. Extra Features**

### 1. UV Texture Mapping (1.0)

**Results:** 

**checkerboard:**

![checkerboard texture rasterization](https://lh3.googleusercontent.com/--eh0A_fp1wE/WeJ-By5iepI/AAAAAAAABE8/do-2zKpamLUEU9uwTLcWtqtp5XDQ8giYwCLcBGAs/s0/UVcheckerboard.gif "UVcheckerboard.gif")

**duck:**

![duck texture rasterization](https://lh3.googleusercontent.com/-w3tHNJfKIj4/WeK8mJ5H9-I/AAAAAAAABFo/Hz7GA1gO80wYUicZNnjpZZBTac4_JcrkgCLcBGAs/s0/UVduck.gif "UVduck.gif")

**CesiumMilkTruck:**

![CesiumMilkTruck texture rasterization](https://lh3.googleusercontent.com/-QYGDsGXlnak/WeK8MvSz2kI/AAAAAAAABFg/UFgK1HsnQgMW7W4vfA-vMF68ZpNelEXUgCLcBGAs/s0/UVCesiumMilkTruck.gif "UVCesiumMilkTruck.gif")

### 2. Additional Primitive: Lines (0.5) 

The way to implement Lines is to only rasterize pixels that lies on the lines between vertices of the triangles rather than rasterize all points on the triangle. The tolerance of pixels that "lies on" the line is the dot product of the vectors between a specific pixel point to two vertices is smaller than -1 + 0.02, which means the angle between those vectors are larger than 170 degrees.

To test this feature, please change at the beginning of **rasterize.cu** into true, and remember to change it back before testing other features. 

    #define USINGLINES false

**Results:** 

**box:**


(170 degrees of tolerance)


(FLT_EPSILON tolerance)


### 3. Additional Primitive: Points (0.5)

The way to implement Point clouds is to only rasterize vertices on the triangle rather than rasterize all points on the triangle.

To test this feature, please change at the beginning of **rasterize.cu** into true, and remember to change it back before testing other features. 

    #define USINGPOINTS false

**Results:** 

**duck:**

![duck point rasterization](https://lh3.googleusercontent.com/-EpRsvGCk_dM/WeLExW6T8YI/AAAAAAAABGE/HmGk2HY126kDhmZYUsBbp7dY3ZG1nqSYACLcBGAs/s0/PointDuck.gif "PointDuck.gif")

## **3. Performance Analysis**

**Bottleneck of performance:**


*Improvement*: Using shared memory to perform.

The comparison between using global memory and shared memory.


### Credits

* [tinygltfloader](https://github.com/syoyo/tinygltfloader) by [@soyoyo](https://github.com/syoyo)

* [glTF Sample Models](https://github.com/KhronosGroup/glTF/blob/master/sampleModels/README.md)

