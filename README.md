This first line is a quick description for User Messages. Limit of 20 chars.
The second line in the User Messages box reports the auton number.

Supported methods:

driveBasic(relative, start type, start param, end type, end param, driveSpeed, [label])
driveBasicOneSide(relative, start type, start param, end type, end param, driveSpeed, left/right, [label])
driveManual(relative, start type, start param, end type, end param, leftDriveSpeed, rightDriveSpeed, [label])
testFunct(relative, start type, start param, end type, end param, [label])
shifterSet(relative, start type, start param, "low"/"high")
intakeRun(relative, start type, start param, end type, end param, [label])
intakeOff(relative, start type, start param, end type, end param, [label])
shooterSetRPM(relative, start type, start param, speed)
armSet(relative, start type, start param, potPosition)
driveBasicGyro(relative, start type, start param, end type, end param, driveSpeedSecondary, gyroAngle, left/right, [label])

Methods in development:

driveVision(relative, start type, start param, end type, end param, "disc"/"target", driveSpeed, [label])
driveBasicMotionProfile(relative, start type, start param, end type, end param, distance, vprog, t1, t2, [label])
intakeSet(relative, start type, start param, up/down)

Future methods:

intakeRun and intakeOff will also run the loading belts for the rest of the shooter
fireAll(relative, start type, start param, end type, end param, [label])
shooterFireOneSide(relative, start type, start param, end type, end param, left/right, [label])