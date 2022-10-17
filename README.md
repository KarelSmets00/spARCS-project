# spARCS-project
### An ARCS course project proposal for situational aware robotics 
![](./assets/spARCS_logo.svg).

## 

# Proposal
### Ideology
Todays industrial sector stands in front of two chalenges. First, find a way to cope with loss of skill due to retirement. Second, fulfilling the demand on high custimization of products in the pursuit of added value. In general, production machines and processes have to become aware of their operation to be able to run autonomously. This reduces te need for skilled operators and allows 'mass production' of speciality work. Within the spARCS project, the possibility of a situation aware robotic welding sytem is investigated to serve the above mentioned challenges.

### Task
The welding of a fillet weld(s).
### Perception
* Detection of weld feature (feature = one weld with all its characteristics and its adjacent geometry; a CAD model of an assembly to be welded contains a feature for each weld)
    * Using a camera mounted on robot arm 1 
    * Detecting the feature to be welded (features defined by CAD model)
    * Determining the location and rough direction of weld
* Local geometry of weld location
    * Distance sensing lidar mounted on top of the welding torche (located on robot arm 2)   
    ![lidar assited welding arm](./assets/lidar_assisted_welding_arm.svg).
    * Determine the optimal welding position. (Making sure the bead is put in the corner of the weld)

### Environment
* Avoiding collision with:
    * Clamping setup (welding table, clamps, ...)
    * Construction to be welded
    * Other robot arm

### Planning/Control
* Planning:
    * CAD model determines feature to be welded
        * Feature contains weld parameters like length, tortch angle, position of weld in workpiece coordinate system (WCS), ...
    * Determening scanning zone based on scanning strategy:
        * Rough global picture used to plan scanning zone for feature 1
        * Found location of feature 1 could be used to plan scanning zone for subsequent feature 2
    * Planning movement of camara arm to scanning zone and in scanning zone
    * Planning of welding arm trajectory

* Control:
    * Camera arm motion feedback: successive re-evaluation of environment
    * Welding torche feedback: using lidar to keep torche centered in the corner
    ![](./assets/lidar_position_feedback.svg).
    * Weld gap control based on welding current/voltege (dependant on welding process)
    

## Conclusion
Hopefully we 'spARC(s)' some interest ;) 