![alt text](http://d3j5vwomefv46c.cloudfront.net/photos/large/770644740.jpg "Title")

Here is Team 2337’s robot, Crossfire, for the FIRST Robotics Competition's 2013 Game: Ultimate Ascent.

Extensive robot photos taken by Daniel Ernst, and a couple of team members can be found on the [team Google+ page](https://plus.google.com/b/115608715549316219693/115608715549316219693/posts). All of our match videos from inside Michigan are available via the [First in Michigan YouTube channel](http://www.youtube.com/firstinmichigan). 

Any comments and questions are welcome (see the [Chief Delphi discussion](http://www.chiefdelphi.com/forums/showthread.php?t=106664)).

Robot CAD will be uploaded to FRC-Designs (README will be edited to reflect link when it is uploaded).

### **Software highlights:**

-**LabVIEW robot project** managed with **git and hosted by GitHub**. During build season, different projects had different branches, and then we completely manually merged code by hand. 
-**”Cheesy Drive”**, an RC-style drive system where throttle and steering are on separate joysticks on the same gamepad
-For intake belt system control, a **simple state machine** with different states commanded by operator
-**Bang-bang** shooter speed-control with a unique bottom gain, tuned for specific speeds
-**Straight autonomous driving tracking the gyro and gyro turns** for the 7 and 5 disc autonomous modes
-**Data logging to text file** that can be retrieved via the cRIO FTP server. Tracks shooter speed and arm position for checking shots.
-Last year’s **autonomous scripting** system with a **trapezoidal motion profile** algorithm implemented inside [i](not used in competition)[/i]
-**Dashboard-based vision processing** [i](not used in competition)[/i]
-Small usability improvements (from our perspective) **NERDViewer.html** (from FRC254’s 2012 code release's PoofViewer.html) for driver/operator/coach viewing [i](not used in competition)[/i]

### **Robot features:**

-**Four-CIM, SuperShifter-driven** drivetrain in an octagonal shape using the 48/50/60 gearset (slimmed down), direct driven to the center four 4” VexPro **VersaWheels**, and chained out to the same, inline 4” VexPro VersaWheels. Speed should be around 7.5 and 14.5 fps. This is underpinned by our first sheetmetal chassis at ?” inch, with a bottom waterjetted piece and the rest milled.
-From the **ground disc intake**, with two top rollers driven by a BAG motor through a 4:1 VexPlanetary through O-rings. The disc would be lifted off the ground slightly by a lexan lip, and then once the roller made contact, the lip would actuate upward with the disc to keep it moving.
-A large arm driven by a **linkage similar to FRC67 from 2007 and FRC148 from 2011**. Powered by a MiniCIM, through a custom transmission at 335:1 inside the gearbox and through a wire EDM’d central gear (which had a ratio of 12:100 for a final ratio of 2790).
-On the arm, a **rubber-band disc management system** with an upper tray to transfer discs to the two lower trays. The top part and bottom parts are driven separately, each by a AM 550 through a  VexPlanetary at a 5:1 and then through timing belts.
-A **double-shooter** that can shoot two discs out at once, or one at a time. Each shooter is a **single AM 8” pneumatic wheel with about 90 degrees** worth of wrap on the disc. The two wheels are direct-driven together by four BaneBot 550s paired together in CIMulators.
-Two lexan hooks for **hanging from level 1**, each powered by a pneumatic cylinder and extra rubber banding.
-Large lexan hood attached to arm for **feeder station loading** and blocking shots while the robot stays below 60".
-**Attachable blocker** that folds down with the arm, and rises up to ~80" (first used at Worlds).

We didn’t look too hard at automated LabVIEW tools for diff and merges - any recommendations would be appreciated. Manual merges were inefficient, not fun, and resulted in refnum naming problems later on. We gave up branching after build season, when a lot of development and tuning happened at competitions, where only one or two programmers were involved, and they would simply work off of the master branch.

### **2013 Competition Season Performance:**

-**Kettering District** Quarterfinalists, seventh alliance - second pick, ranked 26th, Engineering Excellence Award
-**Troy District** Quarterfinalists, sixth alliance - first pick, ranked 12th, District Chairman’s Award
-**Bedford District** Semifinalists, third alliance - second pick, ranked 35th, Gracious Professionalism Award
-**Michigan State Championship** Finalists, first alliance - second pick, ranked 52nd, State Chairman’s Award
-**Championship - Galileo Division** Semifinalists, third alliance - second pick, ranked 46th
