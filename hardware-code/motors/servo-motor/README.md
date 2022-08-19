# Servo Motor

![Servo Motor](../../../.gitbook/assets/Smart\_Robot\_Servo\_Photo\_From\_Bundle\_Shot-noflag\_\_84262.webp)

The Servo Motor is a very small (in comparison) motor that is excellent at low-torque, low-velocity requirements. In addition, the limit capabilities of the Servo Motor can ensure that hard limits (defined by the Servo Programmer) restrain full rotation of the Servo.&#x20;

For example, one might want to use a Servo Motor to control the angle at which a camera is at-the low speed and hard limits will ensure that the camera will not be pushed past its limits.

## Programming the Servo Motor

The video [here](https://youtu.be/PJjFdsnw0uY) will show you how to program the servo for continuous or restricted motion.

{% embed url="https://youtu.be/PJjFdsnw0uY" %}
REV Robotics Servo Demo
{% endembed %}

#### [Buy a new Servo Programmer](https://www.revrobotics.com/rev-31-1108/)

## Operating Modes <a href="#operating-modes" id="operating-modes"></a>

Out of the box, the Servo Motor operates as a 270° servo. However, the Servo Programmer can reconfigure the Servo Motor to set angular limits or switch it into a continuous rotation mode.

### Default Operation <a href="#default-operation" id="default-operation"></a>

The default range for the Servo Motor is 270°. This range is mapped to an input pulse range of 500μs to 2500μs with 1500μs as the center point. The image below describes the pulse-to-angle relationship.

![](https://2589213514-files.gitbook.io/\~/files/v0/b/gitbook-legacy-files/o/assets%2F-M5yw0n8IneF5-9ybLjT%2F-MB\_vrFI\_mJbhAOGXIO5%2F-MB\_yzhf7dnGkYfx6zkp%2FServo\_270\_Range\_Full\_Green-01.png?alt=media\&token=db791fac-0f86-42d8-9651-1c0e42ae87ad)

### Continuous Rotation <a href="#continuous-rotation" id="continuous-rotation"></a>

The Servo can be configured with the Servo Programmer to operate in a continuous rotation mode. In this mode, the same input pulse range is mapped to direction and speed. The table below lists the pulse mapping for direction and speed.

![](https://2589213514-files.gitbook.io/\~/files/v0/b/gitbook-legacy-files/o/assets%2F-M5yw0n8IneF5-9ybLjT%2F-M8WQp\_aU3jlfmzyZA5V%2F-M8WUtfWcre4DktYBnv0%2FScreenshot%20\(13\).png?alt=media\&token=0483c54f-8ec2-4be0-a3e8-b5dd3374655a)

### Angular Limits <a href="#angular-limits" id="angular-limits"></a>

The Servo can be easily configured with the Servo Programmer to limit right and left motion at two user-defined angles. Input pulses that occur past the limits will be ignored and the Servo will hold the limit angle. Any two angles can be set as limits as long as the left limit is left of the center dead band and the right limit is to the right of the center dead band. The table below shows the valid regions for left and right limits.

![](https://2589213514-files.gitbook.io/\~/files/v0/b/gitbook-legacy-files/o/assets%2F-M5yw0n8IneF5-9ybLjT%2F-MB\_vrFI\_mJbhAOGXIO5%2F-MB\_z21vt7t6VYO6gk0T%2FServo\_270\_Range\_Limit\_Too\_Close.png?alt=media\&token=05207ceb-7734-400f-9423-eed9fd439aab)

Once valid limits are programmed, the Servo will ignore any pulses that exceed the limits and hold the limit angle. For example, the image below exhibits what would happen if a left limit of -30° and a right limit of +60° was set.**​**

![](https://2589213514-files.gitbook.io/\~/files/v0/b/gitbook-legacy-files/o/assets%2F-M5yw0n8IneF5-9ybLjT%2F-MB\_vrFI\_mJbhAOGXIO5%2F-MB\_z3iQG92g4sFKXPuk%2FServo\_Full\_270\_Range\_And\_Limits-01.png?alt=media\&token=b86e324d-b901-48dc-af88-fca499bb04f7)

## Code

Refer to REV Robotics docs: [here](https://docs.revrobotics.com/duo-control/programming/hello-robot-test-bed/test-bed-blocks#servo-basics)

![The Servo in this example has been configured to be called 'test\_servo'](../../../.gitbook/assets/blocks%20-%20servo%20final%20code.svg)

## [REV Robotics Documentation](https://docs.revrobotics.com/duo-build/actuators/servos/smart-robot-servo)

#### [Buy more here](https://www.revrobotics.com/rev-41-1097/)
