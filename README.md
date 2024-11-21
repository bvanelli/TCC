# TCC

TCC (meaning *Trabalho de Conclusão de Curso*) and was my submission as Bachelor Thesis as final assignment to get the
degree of Control and Automation Engineering. This contains the main source code for thesis itself, and references
to the other projects used to generate results for the thesis. The final version is available for download:

- [Repository entry](https://repositorio.ufsc.br/handle/123456789/196836)
- [PDF version](https://repositorio.ufsc.br/bitstream/handle/123456789/196836/TCC_20182_BrunnoVanelli.pdf)

# Abstract

Robotics has been present in industry for decades now, but the adoption of robots working closely to humans is 
still challenging. Although much has been developed in the field of assistive robots, they are still incipient 
because of all the technology required to interact with users in a meaningful way. This paper aims at discussing a 
specific task in mobile robots, SLAM, or Simultaneous Localization and Mapping. It comprises the ability of the robot 
to map unknown environments while having no previous information. A framework is proposed to methodologically analyse
the mapping results for different SLAM algorithms. The case study will be presented using Care-o-bot, the assistive
robot developed at Fraunhofer IPA. Data from laser scanners and odometry is used, and the resulting reconstruction 
from the most popular algorithms available on ROS (Robot Operating System) will be presented and benchmarked, 
namely Gmapping, Hector, Karto and Cartographer. Comparisons on mean square error and displacement error will be 
calculated for each algorithm, as well as proposed calculations for map distortion and CPU and Memory usage. 
The results show good stats for Gmapping and Cartographer, some of the most popular choices in the ROS community, 
Cartographer having the most accurate maps. Hector and Karto seem alternative options for devices with lower 
computing power, as they can consume far lower CPU on default settings, as well as providing good localization.

Keywords:

1. SLAM
2. Gmapping 
3. Hector 
4. Karto 
5. Cartographer

# Resource list

> [!WARNING]
> It is likely that you might have to do some changes/upgrade ROS versions for these scripts to work on the newest 
> versions of ROS.

The thesis proposes a way to evaluate and compare mapping accuracy of multiple SLAM algorithms. 

The hardware config is available at [bvanelli/cob_robots](https://github.com/bvanelli/cob_robots).

The software and testing config is available at [bvanelli/cob_simulation](https://github.com/bvanelli/cob_simulation).

The maps were generated using a 
[self-written tool in Python](https://github.com/bvanelli/cob_simulation/blob/indigo_dev/cob_bringup_sim/maps/generator.py).

The maps were generated using PNG images with the pixel borders are reference. Here is one example:

[![](https://github.com/bvanelli/cob_simulation/blob/indigo_dev/cob_bringup_sim/maps/test1.png?raw=true)](https://github.com/bvanelli/cob_simulation/blob/indigo_dev/cob_bringup_sim/maps/test1.png)

After running the robot in all generated maps, the raw data from the simulated sensors 
[was saved in ROS bags](https://github.com/bvanelli/cob_simulation/tree/indigo_dev/cob_bringup_sim/bags).

Each one of the SLAM algorithms was run and the results were [stored in the results folder](https://github.com/bvanelli/cob_simulation/tree/indigo_dev/cob_bringup_sim/results)

The comparison was done by lining up the maps with ICP and calculating the score based on the accuracy of the mapping.
The script for comparison [can be found here](https://github.com/bvanelli/cob_simulation/blob/indigo_dev/cob_bringup_sim/results/icp_map_comparison.py).

# Citation

If you want to cite this work, you can use as a baseline the following Bibtex entry:

```bibtex
@mastersthesis{vanelli2019comparison,
    title={Comparison and benchmarking for SLAM in mobile robots},
    author={Vanelli, Brunno},
    year={2019},
    month={June},
    address={Blumenau, SC},
    note={Available at \url{https://repositorio.ufsc.br/handle/123456789/196836}},
    school={Universidade Federal de Santa Catarina},
    type={Bachelor's thesis}
}
```
