Autonomous scripting system documentation:
---

The functions without an end type or end parameter will only execute for one cycle – they tend to simply set different local variables once.  

Functions that have are not **bolded** but *italicized* mean that I personally don't know if they work – don’t use them without testing! They are present in the "autoMaintainCurrentInstructions.vi" that the robot can reference - but they likely don't work properly. Kind of a to-do list and remembrances of past build season ideas.

**Relative vs. Absolute:** relative is supposed to be relative to another command, absolute is relative to the beginning of autonomous. Not sure if absolute works properly, so haven't really touched it.

Current possible data to be used as start types and end types are retrieved (and thus, also defined) in autoGetIOData.vi once per cycle. The utility autoSelectData.vi unpacks data from the cluster that contains all of the data types. The current ones are “e”, the left encoder value, “g”, the gyro angle value, “t”, the elapsed time in autonomous, and “ap”, the current arm string potentiometer value.

* *armSet* (“relative”/”absolute”, start type, start parameter, desiredArmPotPosition, label) - Supposed to be able to set an arm position and "forget about it" - the arm moves automatically to attain and retain the position until a new position is set. Still haven't tuned the arm well enough.

* **armBasic** (“relative”/”absolute”, start type, start param, end type, end param, motorPowerToSet, label) Drive the arm motor with the desired power to set until the end parameter is triggered.

* **armPosition** (“relative”/”absolute”, start type, start param, end type, end param, desiredArmPotPosition, label) - The difference between "armSet" and "armPosition" is that armSet runs forever (if code setting armPID variable to true is added)

* **driveBasic** (“relative”/”absolute”,  start type, start param, end type, end param, motorPowerToSet, label) - multiplies the left side of the drivetrain by “driveStraightConstant” as set in the config.ini file

* **driveBasicGyro** (“relative”/”absolute”, start type, start param, end type, end param, motorPowerToSetSecondarySide, desiredRawGyroAngle, “left”/”right”/”both”) - This function was used for turns where one side is controlled by a PID on gyro angle (config.ini constants gyroTurnP, I, and D) and the other side (the one not defined as a function parameter) had a constant power.

* **driveStraightGyro** (“relative”/”absolute”, start type, start param, end type, end param, secondaryMotorPowerToSet, “left”/”right”/”both”, label) - Using config.ini constants “straightGyroProportion/I/D”, lock onto gyro heading of 0 degrees by varying left/right/both sides

* *driveStraightVision* (“relative”/”absolute”, start type, start param, end type, end param, motorPowerToSetSecondary, “left”/”right”, label) - Same as driveStraightGyro, but use vision tracking data and a PID on that instead

* *driveBasicMotionProfile* (“relative”/”absolute”, start type, start param, end type, end param, label) - Execute a triangular motion profile on the robot from reading the motion profile arrays and performing the modified PID calculation in “autoMotionProfileMain” used by FRC 254/971 to figure out motor output. Never, ever tested.

* **driveBasicOneSide** (“relative”/”absolute”,  start type, start param, end type, end param, motorPowerToLeft, motorPowerToRight, label) - simple motor power write (number from -1 to 1) to each side of drivetrain

*  *driveManual* (“relative”/”absolute”, start type, start param, end type, end param, motorPowerLeft, motorPowerRight, label) - sends motor power to each side of DT, then adds additional factor from a PID based off of the difference in encoder counts (looking for a straight drive). Not taken out from 2012, PID parameters not in config.ini

* **driveVision** (“relative”/”absolute”,  start type, start param, end type, end param, motorPowerToSend) - An old (probably 2012) driveStraightVision, with zeroes plugged in for vision inputs.

* **gyroReset** (“relative”/”absolute”,  start type, start param, label) - Calls the GyroReset vi, or re-zeroes it like a scale.

* **beltsFeed** (“relative”/”absolute”,  start type, start param, end type, end param, label) - Runs feeder, queuer motors forward and the bottom intake in reverse just in case

* **beltsGround** (“relative”/”absolute”,, start type, start param, end type, end param, label) - Runs all intake motors forward – for ground pickup

* **beltsOff** (“relative”/”absolute”,  start type, start param, end type, end param, label) - Writes zeroes to the intake, feeder, and shooter queuer motors.

* **shifterSet**(“relative”/”absolute”, start type, start param, “high”/”low” label) - Sets drive gear in desired location.

* **shooterSetRPM** (“relative”/”absolute”, start type, start param, rpmValue, label) Set RPM to desired value, and automatically turns on the shooter. To turn off the shooter, set RPM to zero.

* **shooterFire** (“relative”/”absolute”,  start type, start param, end type, end param, “top”/”bottom”/”both”, “shotgun”/”machinegun”, label) - Fires shots using the Periodic Tasks-defined shotgun and machinegun modes (I believe machinegun is deprecated currently)to manipulate the pistons, and the specified location. Automatically turns on the shooter queuer belts too.

* **shooterStopFire** (“relative”/”absolute”,  start type, start param, end type, end param, label) - Turns off the shooter queuer belts, retracts all the pistons by setting all positions and shooting modes to false.

* **testFunct** (“relative”/”absolute”, start type, start param, end type, end param, label) - Just acts as a time delay if necessary, perhaps for cascading actions off of each other.