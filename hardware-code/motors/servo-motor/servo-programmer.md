---
description: (Docs from REV)
---

# Servo Programmer

![](../../../.gitbook/assets/assets\_15mm\_-M8WcLi6koTauMV2xJ63\_-M8WdOZiJLaHBzbA2oeW\_1.png)

The Servo Programmer is used to program the Servo Motor. The programmer defines the limits of the Servo Motor or sets it into continuous mode.

## Operating Modes&#x20;

The Servo Programmer has several operating modes for configuring and testing the REV Smart Robot Servo. The following sections describe each operating mode in detail.

### Switching Modes

Follow the steps below to switch a REV Smart Robot Servo between Continuous Mode and Servo Mode. The figure below shows the process to select Continuous Mode.

![](<../../../.gitbook/assets/Screenshot (25).png>)

1. Connect the Servo to the programmer.
2. Turn on the programmer.
3. Slide the mode switch to the desired mode: C - Continuous, S - Servo.
4. Press and release the PROGRAM button once.
5. The PROGRAM LED should blink and then stay solid indicating success.

### Setting Angular Limits&#x20;

Follow the steps below to set the angular limits for the Servo Mode. The figure below shows an example of setting a left and right limits at -30° and +60° respectively.

![](<../../../.gitbook/assets/Servo\_Full\_270\_Range\_And\_Limits-01 (1).png>)

Start with the Servo already configured in Servo Mode, see section [Switching Modes](servo-programmer.md#switching-modes) for instructions.

1. Connect the Servo to the programmer.
2. Turn on the programmer.
3. Slide the mode switch to S position.
4. This step is optional, but recommended to make it easier to see the valid limit ranges. Please refer to the Servo User's Manual for more information about the valid limit ranges.
   1. Press and release the TEST button twice to enter Manual Test Mode (see [Test Modes](servo-programmer.md#test-modes) for more information).
   2. Press the PROGRAM button to center the servo at 0°.
   3. Press and release the TEST button once to leave the test mode.
5. Manually rotate the servo to the desired left limit position.
6. Press and release the LEFT button. The LEFT LED will illuminate if the position is valid.
7. Manually rotate the servo to the desired right limit position.
8. Press and release the RIGHT button. The RIGHT LED will illuminate if the position is valid.
9. After both limits are set, press and release the PROGRAM button. The PROGRAM LED should blink and then stay solid indicating success.

### Resetting to Default&#x20;

Follow the steps below to reset the Smart Robot Servo to its default mode and limits. The figure below shows the process to reset to defaults.

![](../../../.gitbook/assets/Servo\_270\_Range\_Full\_Green-01.png)

1. Connect the servo to the programmer.
2. Turn on the programmer.
3. Slide the mode switch to S position.
4. Press and hold the PROGRAM button for at least 5 seconds.
5. The LEDs will blink and then the PROGRAM LED will stay solid indicating success.

## Test Modes&#x20;

In either Continuous or Servo Modes, pressing and releasing the TEST button cycles through the two test modes:

* 1st press - Automatic Sweep Mode
* 2nd press - Manual Test Mode
* 3rd press - Return to default state

The section below will cover the two different test modes.

{% tabs %}
{% tab title="Automatic Sweep Mode" %}
In Automatic Sweep Mode, the Servo Programmer will automatically sweep the Servo through motions appropriate for its configuration. the table below describes the behavior based on the configured mode.

| **Servo and Programmer Mode** | **Behavior**                 |
| ----------------------------- | ---------------------------- |
| **Continuous Mode (C)**       | Sweeping direction and speed |
| **Servo Mode (S)**            | Sweeping between limits      |
{% endtab %}

{% tab title="Manual Test Mode " %}
In Manual Test Mode the LEFT, PROGRAM, and RIGHT buttons control the movement of the SRS. The table below describes how the SRS will behave based on the configured mode.

![](<../../../.gitbook/assets/Screenshot (29).png>)
{% endtab %}
{% endtabs %}

### Power-off Reminder

If the Servo Programmer is left on for an extended period of inactivity, it will blink every LED as a reminder to shut off power.

## Video Explanation

{% embed url="https://youtu.be/PJjFdsnw0uY" %}
REV Robotics Servo Programmer Explanation
{% endembed %}

## [REV Robotics Documentation](https://docs.revrobotics.com/duo-build/actuators/servos/srs-programmer)
