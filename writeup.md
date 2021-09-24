**PID Control Project**

The goals / steps of this project is to build a PID controller and tune the PID hyperparameters by applying the general processing flow so that the the vehicle is able to drive successfully around the track.


[video1]: ./pid.mkv


### Compilation
Code complies correctly.


### Implementation

The PID implementation is done on the ./src/PID.cpp. The PID::UpdateError method calculates proportional, integral and derivative errors and the PID::TotalError calculates the total error using the appropriate coefficients.

### Reflection

#### Describe the effect each of the P, I, D components had in your implementation.

* The proportional portion of the controller tries to steer the car toward the center line. If used along, the car overshoots the central line very easily and go out of the road very quickly.
* The integral portion tries to eliminate a possible bias on the controlled system that could prevent the error to be eliminated. If used along, it makes the car to go in circles.
* The differential portion helps to counteract the proportional trend to overshoot the center line by smoothing the approach to it.

#### Describe how the final hyperparameters were chosen.

The parameters were chosen manually by try and error. First, make sure the car can drive straight with zero as parameters. Then add the proportional and the car start going on following the road but it starts overshooting go out of it. Then add the differential to try to overcome the overshooting. The integral part only moved the car out of the road; so, it stayed as zero. After the car drove the track without going out of it, the parameters increased to minimize the average cross-track error on a single track lap. The final parameters where [P: 1.5, I: 0.0, D: 2.5].


### Simulation

#### The vehicle must successfully drive a lap around the track.

Here's a [link to my video result][video1]
