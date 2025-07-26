# LZ's VNyan Camera Controller

Control a camera using keyboard hotkeys or a gamepad!

![Example 1](examples/camcontrollerexample1.gif)

*controller pose not included*

To use this, trigger <b>SpawnCamera</b> and the camera should swap to the new view. Use your keyboard hotkey controls to move the camera around. If you want to use your gamepad, use the <b>ControlMode</b> toggle. There is also a Speed multipler parameter, CamMultiplier, you can use to speed up or slow down movement. On gamepad this is controlled with RB/LB. 

The idea with this was partly to get position/rotation transforms for camera's that you could save and use for reference. Positioning with VNyan's Default camera can be tricky at times if you want to get a specific spot and angle. With this you can position your camera more intuitively, then check it's location. *also this was made to control a camera, but you could control *any* custom object with this.*

![Example 2](examples/camcontrollerexample2.gif)

Included under [Camera Objects](/Camera%20Objects) are a couple pre-made custom objects to use, one using VNyan's built-in camera component, and the other outputting to a separate Spout2 source. There is some info there too about how to create your own Camera's in VNyan.

## Settings
The right goup are the Main Settings, which are the custom object node, base speed, acceleration and deacceleration. Make sure it's set to spawn VNyanCam.

The left node group has toggles and controls to manage the camera.

### Toggles
- <b>ControlMode</b> - 1 = keyboard, 2 = gamepad
- <b>ControlToggle</b> - 1 = controls on, 2 = controls off
- <b>ToggleCamera</b> - spawn camera object & start controls at default location or destroy it.
- **ResetPosition**, **ResetRotation**, and **ResetCamera** (all settings)
- **SaveCameraTransform **-  save the XYZ position and rotation to the text parameter `CameraTransform`

## Controls
### Keyboard
- SHIFT + WASD = move forward/backward/left/right
- SHIFT + QE = rotate left/right
- SHIFT + RF = move up/down
- CTRL + WS = rotate up/down
- CTRL + RF = twist left/right

### Gamepad
- Left stick = move forward/backward/left/righ
- Right stick = rotate left/right, move up/down
- RB = Speed Up
- LB = Slow down
- LT/RT = rotate down/up
- DLeft = Reset all
- DUp = Reset position
- DDown = Reset Rotation
- X/Y = Twist
