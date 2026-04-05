# Introduction to the MuJoCo Simulator Workshop - Edited

This repository is forked from the [Introduction to the MuJoCo Simulator Workshop](https://github.com/willcforte/Introduction-to-MuJoCo-Workshop) by [Will C. Forte](https://willcforte.com/) for a workshop held at the Rutgers N2E Robotics club.


This was made so I could learn and understand MuJoCo for my master's thesis. This includes experimenting with models and Python scripts to observe behavior changes and getting familiar with the MuJoCo workflow.

Please refer to the original branch for the original workshop contents. 


## Setup

Prerequisites: MuJoCo (Python API), numpy, matplotlib

The files modified are **only** in the `exercises` directory:
- Position
    - `og_postion_PID.py` - original PID gains with extra logging capability
    - `position_PID.py`
- Motor
    - `og_postion_PID.py` - original PID gains with extra logging capability
    - `position_PID.py`
<br>  <br />

Running: 
- The scripts will load the MuJoCo passive viewer GUI for simulation. After 500 simulation timesteps, graphs will generate and save to the `exercises/*PIDpics` folders. Simulations will continue running until user-terminated.
- Make sure to change the actuator scheme based on the script. e.g., if you are running `position_PID.py`, make sure the motor actuators in `2R_robotic_arm.xml` are commented out and position actuators are uncommented.


## Key Changes
- Gains
    - The original scripts uses a single set of gains for both joints. This can assume both joints have the same properties (inertia, friction, weight, etc.)
    - The new scripts uses arrays to specify different gains for each joint. These are also further tuned. 
- Logging
    - Original script tracks: target joint trajectories + control signals
    - New script tracks: target joint trajectories + actual joint positions





## Position

`og_postion_PID.py`
- j1: 3.14 sin... for desired trajectory
- j2 1.57 cos... for desired trajectory
- 1 set of PID gains for both 
<br>  <br />

`position_PID.py`

V1 (PIDforbothJ.png)
- j1: 3.14 sin... for desired trajectory
- j2: 1.57 cos... for desired trajectory
- specific PID gains for each

V2 (PIDforBoth_and_sinforJ2.png)
- j1: 3.14 sin... for desired trajectory
- j2: 1.57 sin... for desired trajectory
- specific PID gains for each, tuned: Kp=[50,80], Ki=[18,20], Kd=[2,1]







<table style="width:100%">
  <tr>
    <td align="center">
      <a href="exercises/posPIDpics/og_pos_fullView.png">
        <img src="exercises/posPIDpics/og_pos_fullView.png" width="150%" title="Click to enlarge">
      </a>
      <br>
      <sup>Original Positional PID Control (Full View)</sup>
    </td>
    <td align="center">
      <a href="exercises/posPIDpics/og_pos_zoomView.png">
        <img src="exercises/posPIDpics/og_pos_zoomView.png" width="150%" title="Click to enlarge">
      </a>
      <br>
      <sup>Original Positional PID Control (Zoomed)</sup>
    </td>
  </tr>
</table>


<div align="center">
  <a href="exercises/posPIDpics/PIDforbothJ.png">
    <img src="exercises/posPIDpics/PIDforbothJ.png" width="500" title="Click to enlarge">
  </a>
  <br>
  <sup>V1 PID Position (Click image to open file)</sup>
</div>

<div align="center">
  <a href="exercises/posPIDpics/PIDforBoth_and_sinforJ2.png">
    <img src="exercises/posPIDpics/PIDforBoth_and_sinforJ2.png" width="500" title="Click to enlarge">
  </a>
  <br>
  <sup>V2 PID Position (Click image to open file)</sup>
</div>










## Motor

`og_motor_PID.py`
- 1 set of PID gains for both 
<br>  <br />

`position_PID.py`
- specific PID gains for each, tuned



<table style="width:100%">
  <tr>
    <td align="center">
      <a href="exercises/motorPIDpics/og_motor_fullView.png">
        <img src="exercises/motorPIDpics/og_motor_fullView.png" width="150%" title="Click to enlarge">
      </a>
      <br>
      <sup>Original Motor PID Control (Full View)</sup>
    </td>
    <td align="center">
      <a href="exercises/motorPIDpics/og_motor_zoomView.png">
        <img src="exercises/motorPIDpics/og_motor_zoomView.png" width="150%" title="Click to enlarge">
      </a>
      <br>
      <sup>Original Motor PID Control (Zoomed)</sup>
    </td>
  </tr>
</table>


<div align="center">
  <a href="exercises/motorPIDpics/newMotor.png">
    <img src="exercises/motorPIDpics/newMotor.png" width="500" title="Click to enlarge">
  </a>
  <br>
  <sup>New PID Motor (Click image to open file)</sup>
</div>
