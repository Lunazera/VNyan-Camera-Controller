# LZ'z VNyan Camera Controller

Control a camera using keyboard hotkeys or a gamepad!

![Example 1](examples/camcontrollerexample1.gif)

*controller pose not included*

To use this, trigger <b>SpawnCamera</b> and the camera should swap to the new view. Use your keyboard hotkey controls to move the camera around. If you want to use your gamepad, use the <b>ControlMode</b> toggle. There is also a Speed multipler parameter, CamMultiplier, you can use to speed up or slow down movement. On gamepad this is controlled with RB/LB. 

The idea with this was partly to get position/rotation transforms for camera's that you could save and use for reference. Positioning with VNyan's Default camera can be tricky at times if you want to get a specific spot and angle. With this you can position your camera more intuitively, then check it's location. *also this was made to control a camera, but you could control *any* custom object with this.*

![Example 2](examples/camcontrollerexample2.gif)

## Settings
The right goup are the Main Settings, which are the custom object node, base speed, acceleration and deacceleration. Make sure it's set to spawn VNyanCam.

The left node group has toggles and controls to manage the camera.

### Toggles
- <b>ControlMode</b> (keyboard, gamepad, or nothing)
- <b>ControlToggle</b> to quickly turn on and off controls
- <b>ToggleCamera</b> to spawn camera & start controls at default location or destroy it.
- Triggers to <b>ResetPosition, ResetRotation, and ResetCamera (all settings)
</b>
<b>SaveCameraTransform </b>trigger will save the XYZ position and rotation to the text parameter <CameraTransform>

## Controls
### Keyboard
SHIFT + WASD = move forward/backward/left/right
SHIFT + QE = rotate left/right
SHIFT + RF = move up/down
CTRL + WS = rotate up/down
CTRL + RF = twist left/right

### Gamepad
Left stick = move forward/backward/left/righ
Right stick = rotate left/right, move up/down
RB = Speed Up
LB = Slow down
LT/RT = rotate down/up
DLeft = Reset all
DUp = Reset position
DDown = Reset Rotation
X/Y = Twist
