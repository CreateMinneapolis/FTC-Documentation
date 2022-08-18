# 🔌 External I2C Devices

![The location and pinout of the I2C ports](../../.gitbook/assets/Control\_Hub\_Port\_Specific\_Pinout\_I2C\_LARGER\_SIZE-01.png)

A variety of I2C devices can be connected to the Control/Expansion Hubs. These devices do not need to be "REV Robotics" sensors--they can be 3rd-party sensors. This is helpful if the sensors provided by REV do not meet the needed specifications.&#x20;

{% hint style="info" %}
A list of common external sensors can be found [here](https://docs.revrobotics.com/duo-control/sensors/5v-sensors/sensor-compatibility-chart).
{% endhint %}

Sensor feedback to the Hub works differently for the I2C sensor than it does for Analog or Digital sensors. With the Analog and Digital Sensors, only one communication channel needs to be used by an individual sensor. In contrast, an I2C sensor sends different kinds of information over the SDA (white) and SCL (blue) wires. Since the I2C is transferring more complex data to the Hub then Analog or Digital sensors, there has to be a component of harmonization, or consistency, as the data moves from the sensor to the Hub. The **SCL (Serial Clock)** channel provides consistency by acting as a clock line and time-stamping the data provided by the **SDA (Serial Data)** channel.

{% hint style="warning" %}
If a sensor requires 5V of power, a logic level converter will be required to step up the voltage from 3.3V to 5V.&#x20;
{% endhint %}

## Configuration

Before a sensor can be programmed it must be added to the Robot Configuration. The configuration file stores all configured devices in the Control Hub's "hardwareMap," which can be called to in the code to establish the line of communication between devices.&#x20;

In order to function, all FTC legal I2C devices have drivers installed into the SDK. With regards to configuration, this means that the device has to be set to the drop-down menu item that corresponds with its drivers. Visit the datasheet for the sensor you are trying to configure to see how to configure it.&#x20;

The steps below shows a basic configuration for I2C **** devices. The I2C Bus 0 hosts the internal[ IMU](bno055-imu-inertial-measurement-unit.md) sensor within the Hubs. In this example, the Color Sensor V3 is being added to Bus 0 as well.&#x20;

#### Step 1

While in the configuration select the **I2C Bus 0** option. This will open a screen that shows the IMU.

![](<../../.gitbook/assets/i2c sensor config step 1.svg>)

#### Step 2

Press the Add button to add the Color Sensor to this bus. Select "REV Color Sensor V3" from the drop-down menu and name the device.

![](<../../.gitbook/assets/i2c sensor config step 2.svg>)

#### Step 3&#x20;

When you have finished configuring the sensor hit **Done**. The app will return to the previous screen.

## [REV Robotics Documentation](https://docs.revrobotics.com/duo-control/sensors/i2c)
