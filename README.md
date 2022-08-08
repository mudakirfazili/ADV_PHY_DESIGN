# ADVANCE PHYSICAL DESIGN WORKSHOP USING SKYWATER 130NM PDK

This repository contains the files generated through out the workshop. 

# Table of Contents
- [Introduction](#introduction)
- [Conclusion](#conclusion)
- [Author](#author)
- [Acknowledgements](#acknowledgements)
- [References](#references)

# Introduction

This repository provides a step by step guide of openlane flow.
![flow](images/0.png)
```
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
```

![starting_openlane](images/1.png)

```
run_synthesis
```

![run_synthesis](images/2.jpg)


```
run_floorplan
```
![run_floorplan](images/3.png)

![full](images/picorv32a.floorplan.def.png)
![decoup_caps](images/4.jpg)

```
run_placement
```
![inveretr_magic](images/picorv32a.placement.def.png)
```
magic -T sky130A.tech sky130_inv.mag &
```
![inveretr_magic](images/5.jpg)

```
extract all
ext2spice cthresh 0 rthresh 0
ext2spice
```
![extract](images/6.jpg)

![netlist](images/7.jpg)

```
ngspice sky130_inv.spice 
```
![ngspice](images/8.jpg)
```
plot y vs time a
```
![plot](images/9.jpg)


# Conclusion



# Author
[**Mohammad Mudakir Fazili**](https://www.linkedin.com/in/mudakirfazili14/), *M.Tech Micro-electronics*, NIT Srinagar                                                                                           
*mudakirfazili@gmail.com*

# Acknowledgements
1. [VLSI System Design Corporation](https://www.vlsisystemdesign.com/)
2. [Efabless](https://efabless.com)

A special vote of thanks to **Kunal Ghosh** (founder VSD)
