## Writeup

---

**Path-Planning-Project**
This path planner consists of two main parts which are Trajectory planning and Trajectory generation.

### Trajectory planning
* Frenet coordinate is used to simplify calculation.
* Based on sensorfusion data, the planner can calculate the s distances between ego vehcle and other vehicles.
* is_too_close flag is set to indicate that vehicle in front is within safety range. 
* is_left_lane_occupied and is_right_lane_occupied is set when there are vehicles within safety range on the left and right lane
* when vehicle in front is too close, if left or right lane is not occupied, the vehicle will change lane. If there is no where to change, it will derease speed.
* when there is no vehicle in close front, ego vehicle will pick up speed to max speed.


### Trajectory generation
* spline.h is used for generate a spline
* Previous points are then used for smooth trajectory.
* For remaining points poistion, spline points till the horizon(30m in this project) are taken to interpolate the trajectory.
