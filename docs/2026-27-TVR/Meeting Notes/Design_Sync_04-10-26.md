# Design_Sync_04-10-26 Notes

## Issues Last Year

- Not enough time for proper testing and validation 

**Solution:** Quarterly design plan with design freeze date at least before 1.5 months


- Sensor selection did not cover all the parameter data needed by controls like baro's resolution is too low to detect takeoff and landing, GNSS resolution too low for 3D mapping etc.

**Solution:** LiDAR to detect takeoff and landing, RTK-GNSS for high resolution 3D surveying and UWB for indoor 3D Mapping


- Almost no sensor validation

**Solution:** Firmware to do IMU and Baro raw data validation as soon as possible, MAG noise characterisation as well.


- Didn’t measure accurate gimbal backlash (eye balled it)

**Solution:** TVR Mech to measure backlash of dynamixel - direct drive and indirect drive


- No variable thrust control yet, just static

**Solution:** Differential thrust control will be implemented, active controlled fins explored as well


- Horizontal Battery mounting kept on shifting drone's COM

**Solution:** Vertical battery mounting, aligned across central axis


- We lost lots of points for lack of validation / documentation (justifying decisions)

**Solution:** Wiki is set up and being actively used by TVR

## Hardware

### Backplane:

- Veritcal connector placement on bottom seems to be okay with all

- Considering sticking to parallel battery connectors until custom ESC is ready, alternative is a simple PDB (Under consideration, not a bad idea)

- Design freeze date for backplane is 18/05/26

### Flight Controller

- Sensor raw data validation is top priority

- Antenna interferance was raised, 915Mhz and GNSS Antenna is placed as far way as possible for some isolation

- Refer RC drones / open source designs for sensor selection, especially heading

- Consider optical flow sensor for position hold (Considering for phase 2)

- Add a SD card to store raw sensor data

- Design freeze date for flight controller is 18/05/26

### Battery:

- Tabless cells can give us max 12C which is exactly what we need, so no margin. Still under consideration but likely sticking to existing lipo

- Looking into hot swappable lipo, mech enclosure for our existing lipo to make hot swapping easier

- no conclusion on 12s lipo discussion

## TVR Mech (Rough notes taken from meeting)

These are notes from the first stand-up meeting:

## Github realted
    - Have a ticket request system to grant peoples access to repos and CAD files to edit
    - Add proper checks for assemblies
    - People need to get permission to do changes
    - Have a single froze design
        - Have edits off of a branch of the frozen deisgn, therefore edits are only ever changing the branch off            of the frozen design
        - After the dev-design has been completed then the main frozen branch can be updated
    - Label people who have admin access as "reviewers" and allow reviewers to have admin access
    - Add tags
    - Work with Jason on version related control
## Current design
    - Back lash is the biggest problem
        - A Testing method:
            - Measure backlash via pen and grid
    - Indirect Drive Solutions
        - Higher gear ratio
        - Need to measure backlash
    - Direct Drive Solutions
        - Attach direct and then move components to rectify center off mass
        - Frame would need to possibly expand
        - Needs a design
        - Need to measure backlash
        - Add a “dead mass” as to help move the center of mass
    - Battery Tangent
        - Decrease allowed flight time to remove weight
    - Need more thrust ☹️
    - Next week goal(as of meeting not updated):
        - New gimbal
            - Gear ratio: higher gear ratio to reduce backlash
            - Buy gears (mcmaster-carr) (longer term)
            - Print resin gears (longer term)
        - New leg
            - Come up with a presentable alternative design
    - Constrain montion in center screw of base that allows wiggle
    - Look into thrust vectoring drones that solve current problems
    - Need more external search for solved servo driven design
        - What have people done?
        - Why has it worked?
        - How can we copy and integrate it
    - Leg system
        - Have we looked at other peoples design
        - Do we have more leg designs?
        - Get more leg designs underway (urgent)
        - More consideration of stress concentration on next design
    - Batteries
        - Stop plate
        - Move away from horizontal batteries
        - Look at open sources models to save ourself the trouble
        - Get a better design than the velcro strap
        - Look at rubber on neylon nuts to stop vertical movement
