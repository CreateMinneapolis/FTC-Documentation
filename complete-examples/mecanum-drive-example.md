# ↔ Mecanum Example

![](../.gitbook/assets/MDK\_Default.svg)

```
// Define our code package
package org.firstinspires.ftc.teamcode;


// Import all the necessary scripts so that our code runs
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.DcMotor;
import com.qualcomm.robotcore.hardware.DcMotorSimple;


// Set the "TeleOp" name to something memorable--in this case it is "MecanumDrivetrain"
// The name you choose will be what the program is listed as in the list of TeleOp missions
@TeleOp(name = "MecanumDrivetrain (Blocks to Java)", group = "")
// Define our class as the main function of the program "MecanumDrivetrain"
public class MecanumDrivetrain extends LinearOpMode {

  // List out our private variables. These variables are like containers for our motors--each motor needs a container.
  // Each of our driving motors are listed below:
  private DcMotor cm1;
  private DcMotor cm2;
  private DcMotor cm3;
  private DcMotor cm4;


  // This function is executed when this Op Mode is selected from the Driver Station.
  @Override
  public void runOpMode() {
  
    // These "double" variables are used as power targets for our motors. Later in the code, we will set the motor's speed to the corresponding target. 
    double cm1_target;
    double cm2_target;
    double cm3_target;
    double cm4_target;
    
    // The 'turningPower' variable is used as a scale/stretch factor for rotational movement
    double turningPower;
    
    // The 'powerLimiter' variable is used as a final compression. All outputted values to the motors in the following code will be passed through this limiter.
    double powerLimiter = 0.40;
    
    // The following four lines of code are used to set each 'cm#' variable to it's corresponding motor in the hardware map.
    cm1 = hardwareMap.dcMotor.get("cm1");
    cm2 = hardwareMap.dcMotor.get("cm2");
    cm3 = hardwareMap.dcMotor.get("cm3");
    cm4 = hardwareMap.dcMotor.get("cm4");

    
    // Back left:cm1, back right:cm2
    // Front left:cm3, front right:cm4
    
    // Reverse the necessary drive motors.
    // You will have to determine which motors to reverse for your robot.
    // In this example, the right motor was reversed so that positive
    // applied power makes it move the robot in the forward direction.
    cm1.setDirection(DcMotorSimple.Direction.REVERSE);
    cm2.setDirection(DcMotorSimple.Direction.FORWARD);
    cm3.setDirection(DcMotorSimple.Direction.FORWARD);
    cm4.setDirection(DcMotorSimple.Direction.REVERSE);

    waitForStart();
    if (opModeIsActive()) {
      // Put run blocks here.
      while (opModeIsActive()) {
        // Back left:cm1, back right:cm2
        // Front left:cm3, front right:cm4

        //turning script
        double rotate = 0;
        boolean rotating = false;
        turningPower = 0.85;
        
        // If either our the bumpers are pressed, rotate the robot in that direction.
        if (gamepad1.left_bumper == true) {
            rotating = true;
            rotate = -turningPower;
        } else if (gamepad1.right_bumper == true) {
            rotating = true;
            rotate = turningPower;
        } else {
            rotating = false;
            turningPower = 0;
        }
        
        // Math for full rotational movement (anywhere with the joystick)
        if ((Math.abs(gamepad1.left_stick_x) + Math.abs(gamepad1.left_stick_y) > 0.15) || rotating == true) {
          // To move left, reverse front left and back right
          if (gamepad1.left_stick_x >= 0 && -gamepad1.left_stick_y >= 0) {
            // Quadrant I
            cm1_target = Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (rotate);
            cm2_target = -Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm3_target = Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm4_target = -Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (rotate);
          } else if (gamepad1.left_stick_x < 0 && -gamepad1.left_stick_y > 0) {
            // Quadrant II
            cm1_target = -Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (rotate);
            cm2_target = Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm3_target = -Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm4_target = Math.pow(gamepad1.left_stick_x, 2) + -Math.pow(gamepad1.left_stick_y, 2) + (rotate);
          } else if (gamepad1.left_stick_x <= 0 && -gamepad1.left_stick_y <= 0) {
            // Quadrant III
            cm1_target = -Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (rotate);
            cm2_target = Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm3_target = -Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm4_target = Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (rotate);
          } else if (gamepad1.left_stick_x > 0 && -gamepad1.left_stick_y < 0) {
            // Quadrant IV
            cm1_target = Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (rotate);
            cm2_target = -Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm3_target = Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (-rotate);
            cm4_target = -Math.pow(gamepad1.left_stick_x, 2) + Math.pow(gamepad1.left_stick_y, 2) + (rotate);
          } else {
            cm1_target = rotate;
            cm2_target = -rotate;
            cm3_target = -rotate;
            cm4_target = rotate;
          }
        } else {
          // Reset our motors
          cm1_target = 0;
          cm2_target = 0;
          cm3_target = 0;
          cm4_target = 0;
        }

        // Set the power for our motors (and apply power limiters)
        cm1.setPower(cm1_target * powerLimiter);
        cm2.setPower(cm2_target * powerLimiter);
        cm3.setPower(cm3_target * powerLimiter);
        cm4.setPower(cm4_target * powerLimiter);
        
        // Add telemetry data, so we can observe what is happening on the Driver app
        telemetry.addData("cm1", cm1_target);
        telemetry.addData("cm2", cm2_target);
        telemetry.addData("cm3", cm3_target);
        telemetry.addData("cm4", cm4_target);
        telemetry.addData("rotating", rotating);
        telemetry.update();
      }
    }
  }
}
```

### [REV Robotics Build Guide](https://docs.revrobotics.com/duo-build/mecanum-drivetrain-kit-mecanum-drivetrain)
