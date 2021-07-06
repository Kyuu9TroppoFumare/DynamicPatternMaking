# A Fabric-Simulation based Dynamic 3D Pattern Making system with A full-body Musculoskeletal Physical-Simulation based Adjustable 3D Human Figure Module and A Size Converting Method


[TOC]

##Introduction
This program is aiming at four different topics:
- a method to simulate the **fabric behavior** and the **body-clothing interaction**, especially handling **complex textured curving fabrics** which been created by **fabric modification** and also handling the friction and the deformations of the soft tissues causing by the garments
- an adjustable realistic 3d human figure module reconstructs from **MRI (magnetic resonance imaging)** scans with a physical-simulation based full-body musculoskeletal system that can reproduce **realistic joint-muscle motions** and can be adjusted to fit the body shapes of a wide arrange of individuals by using **medical models of skeletal development**
- a dynamic 3d pattern making system that provides the feasibility of **real-time** adjustment of the clothing pattern and the 3d garments
- a method to handle **size converting** of the garments **from individual to individual** based on the adjustable 3d human figure using **displacement field** and **kernel function**

##How to Use
The program is based on **Cinema 4D**, which contains two separate parts of scripts and a prebuilt adjustable 3d human figure with bones and muscles.

The first part of the scripts are based on **c4dpy** (**Python 2.7**), which function inside Cinema 4D (**R19**), can be directly loaded into Cinema 4d through **Script Manager**.
**For version greater than R19, you might have to convert the Python 2.7 code into Python 3.x code (Python 3.7.7 for Cinema 4D R23)**

Because of the limitations of c4dpy, that not providing support for 3rd party modules and libraries, all the physical-simulation algorithms (the physics engine) function outside of Cinema 4D communicating via **socket**, which could be placed to the cloud server to gain a better performance (especially the performance of GPU version could be benefited from GPU cloud computing with more CUDA cores and larger GPU memory)

There are two versions of the physics engine, the CPU version, and the GPU version, both running on **Python 3.7**.
- The CPU version requires :
   - NumPy (version)
   - SymPy (version)
   - Numba (version)
- The GPU version requires :
   - CUDA environment 
     - CUDA Toolkit (version)
     - cuDNN (version)
   - NumPy (version)
   - SymPy (version)
   - CuPy (version)
   - Numba (version)
 
The communications between original c4dpy and physics engine scripts are via **localhost**. In some scenarios, you probably need to manually change the **port number** in both Cinema 4D and physical engine scripts when scripts conflict with other programs or change the **host** for **cloud computing**.

The computing data of the physical simulations will be transported via a **JSON data **file. When using cloud computing, placing the data file into **NAS (Network-Attached Storage)** for the data transportations is recommended.
You can also modify the scripts to transport computing data via socket as well

##Dynamic System
###Dynamic Object
A polygon object could be labeled into a dynamic object by **Dynamic Object script** with a **Python Tag** that contains all the parameters needed in physical simulation, functions independently and differently from the build-in Dynamic Tag of Cinema 4D.
A base object should be first turned into a polygon object using the **Make Editable** button before being labeled into a dynamic object.
All the polygons must be **quadrilaterals** for the moment.

####Types of the Dynamic Object
Similar to the build-in dynamic system, the types of the dynamic object are as follows :
- **Collider Body**
A steady object that is **undeformable** during the dynamic simulations and collisions, affecting other objects to deform, and **only can be directly moved or deformed by the user**, is used for simulating the objects such as ground, walls, and **the bones in this program**, whose deformations are minimal compared to other objects in the scenario of simulation.

- **Dynamic Body**
   - **Soft Body**
A deformable **solid object** can be affected by gravity and other objects, can be used for simulating elastic objects like muscles and soft tissues of the human body, and also can be used for simulating objects with high hardness such as metal.

   - **Cloth**
A deformable **plane object** can be affected by gravity and other objects, and can be used for simulating such as skins and fabrics.




###Dynamic Environment

###Dynamic Connector

##Cloth & Pattern System

##3D Human Figure
###Posing 
>Update needed

###Adjustment of Body Shape
>Update needed

###Size Converting Method

###Build your own Adjustable Figure

##Algorithm of Dynamic System
###3D Co-Rotation FEM

###Collison & Friction

###Pattern Adjusting

### Size Converting

##Other Usages of Dynamic System

##Benchmark & Comparision

##Extra Tools for C4Dpy

##Future Development
