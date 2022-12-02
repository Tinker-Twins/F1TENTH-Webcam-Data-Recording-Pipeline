# F1TENTH Webcam Data Recording Pipeline

| ![Indoor F1TENTH Vehicle](https://github.com/Tinker-Twins/F1TENTH-Webcam-Data-Recording-Pipeline/blob/main/Media/Indoor%20F1TENTH%20Vehicle.png)|![Outdoor F1TENTH Vehicle](https://github.com/Tinker-Twins/F1TENTH-Webcam-Data-Recording-Pipeline/blob/main/Media/Outdoor%20F1TENTH%20Vehicle.png)|
| :----------------------------------: | :----------------------------------------------------------------------------------: |
| Indoor F1TENTH Vehicle | Outdoor F1TENTH Vehicle |

## SETUP

1. Clone this repository.
    ```bash
    $ git clone https://github.com/Tinker-Twins/F1TENTH-Webcam-Data-Recording-Pipeline.git
    ```
2. Move the `f1tenth` directory to the source space (`src`) of the Catkin workspace on the vehicle computer.
    ```bash
    $ mv ~/Vehicle\ Software/f1tenth ~/catkin_ws/src/
    ```
3. Build the packages.
    ```bash
    $ cd ~/catkin_ws
    $ catkin_make
    ```

## USAGE

- **Teleoperation:** Launch the `teleop.launch` file. Refer [this document](https://github.com/Tinker-Twins/F1TENTH-Webcam-Data-Recording-Pipeline/blob/main/Vehicle%20Software/f1tenth/racecar/racecar/launch/teleop_readme.txt) for detailed information.
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
