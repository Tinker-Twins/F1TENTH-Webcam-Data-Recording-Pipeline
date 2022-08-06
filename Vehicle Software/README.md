# F1TENTH Vehicle Software

This directory hosts the ROS-based software for F1TENTH vehicle's onboard computer, which supports the following key functionalities (amongst others):
- Teleoperation of the F1TENTH vehicle with velocity constraint
- Reading RGB frames from a USB webcam
- Throttled data recording of camera frames, throttle commands and steering commands

## SETUP

1. Clone this repository.
    ```bash
    $ git clone https://github.com/Tinker-Twins/F1TENTH-Webcam-Data-Recording-Pipeline.git
    ```
2. Move the `f1tenth` directory to the source space (`src`) of the Catkin workspace on the vehicle computer.
    ```bash
    $ mv ~/ROS\ Package/f1tenth ~/catkin_ws/src/
    ```
3. Build the packages.
    ```bash
    $ cd ~/catkin_ws
    $ catkin_make
    ```

## USAGE

- **Teleoperation:** Launch the `teleop.launch` file. Refer [this document](https://github.com/Tinker-Twins/F1TENTH/blob/main/Vehicle%20Software/f1tenth/racecar/racecar/launch/teleop_readme.txt) for detailed information.
  ```bash
  $ roslaunch racecar teleop.launch
  ```

- **Webcam Bringup:** Launch the `webcam.launch` file. Launches RViz window to show live webcam feed.
  ```bash
  $ roslaunch usb_cam webcam_bringup.launch
  ```

- **Data Recording:** Launch the `data_recording.launch` file. Launches `teleop.launch` as well as `webcam.launch` files, and records data in a `f1tenth_<time_stamp>.bag` file.
  ```bash
  $ roslaunch racecar data_recording.launch
  ```
