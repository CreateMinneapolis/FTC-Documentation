# 🔃 BNO055 IMU (Inertial Measurement Unit)

There is already an absolute orientation sensor built-in to the robot. It uses the I2C interface to read/write data to the robot.&#x20;

You can add more of these sensors by connecting each additional one to an I2C port and obtaining the address.&#x20;

### Accessing the Built-in Sensor

**Expansion Hubs purchased AFTER December 2021 no longer include an internal IMU**

![](../../.gitbook/assets/image-2.png)

{% hint style="info" %}
The internal address of this sensor is `0x28.` It can use any port.
{% endhint %}

For more information on connecting to the sensor, refer to the [REV Documentation](bno055-imu-inertial-measurement-unit.md#rev-robotics-documentation) or the [I2C page](external-i2c-devices.md).

### Connecting Additional Sensors

Additional IMU's can be added via the I2C ports on the right side of the Control Hub.&#x20;

{% hint style="info" %}
For more information about connections, refer to the I2C [pinout](external-i2c-devices.md)
{% endhint %}

#### Device Search

Because we know that this device has an address of `0x28`, we just need to determine the port so we can read data from the IMU. [This is determined by your configuration.](external-i2c-devices.md#step-1)

## Reading Data from IMU

After our configuration is setup correctly, we can read data from the IMU.

{% hint style="info" %}
For an example of this in action, simply select the 'IMU' template when creating a new program.
{% endhint %}

### [REV Robotics Documentation](https://docs.revrobotics.com/duo-control/sensors/i2c/imu)
