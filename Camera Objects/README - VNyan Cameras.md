# Custom Camera Objects
VNyanCam.vnobj is a simple GameObject with VNyan's camera script on it, which will switch your VNyan window view from the default camera to the new one.

SpoutCam1080p.vnobj is a separate Camera object that won't override VNyan's camera. Instead, it outputs to a Spout2 source called Cam1080p. You can capture this using OBS with the [Spout plugin](https://github.com/Off-World-Live/obs-spout2-plugin)

## Making your own VNyan Spout Camera object
You can have multiple different camera's set up in VNyan that can output to different spout2 captures. These can be recorded in OBS at the same time :3 You can also hide or show different layers in VNyan from being VNyan, like if you wanted a camera that didn't show any props or other effects.

It does increase performance by a bit (you end up rendering many things twice) so you'll have to be careful how you use this.

You're just going to make a VNyan Custom Object with a Unity Camera and Spout Sender in Unity. You'll need the [KlakSpout](<https://github.com/keijiro/KlakSpout>) plugin and the VNyan SDK (and make sure you have Unity's Post Processing package active).
1. Create a new render texture in your project files (under Create > Render Texture).
  - Set the Render Texture size to whatever resolution you want (ie 1920x1080)
  -  Set Anti-aliasing to `None`, and Color Format to `R32G32B32A32_SFLOAT`
2. Create a new Camera in your scene 
  - Set Clear Flags  to `Solid Color`
  - Set Background Color to black with 0 alpha
  - Set what you want your Field of View to be, or click `Physical Camera` to adjust it further (if you want to match the Focal Length setting in VNyan you can set that here)
  - Set Clipping Planes Near to a smaller number to avoid model clipping
  - Set Target Texture to your Render Texture you created.
3. Add a Post-Processing Layer component to the camera
  - Set your Anti-Aliasing mode
  - Set the Layer to Post-Processing/layer 8 (you might need to set this up, see below)
4. Add a Spout Sender component to the camera
  - Set Capture Method to `Texture`, and Source Texture to the same Render Texture as before.
5. Export the camera object as a VNyan custom object

That's mainly it! Once you bring this into VNyan and it's visible, you should see the name that you gave the camera under your Spout2 sources.

If you want to control something like focal length you can set up an animation and control it with a parameter. Use the VNyan Anim Param Link to control it from within VNyan :3

### VNyan Rendering Layers
By default the camera's Culling Mask setting will be `Everything`, but you can change this to choose which layers you want to be rendered in the camera. If you click the Layer dropdown near the top right of the Inspector tab, you will see all the named/setup layers, and `add layer` at the bottom to setup new layers. VNyan internally is already using many of these layers for rendering post-processing effects, droppables, props, etc. You can set up these layers in Unity here, then use the Culling Mask setting to choose which layers you want to be shown in the camera.

I don't know what *all* of the rendering layers in VNyan are, but here are the ones that I know about that Suvi shared at some point:
- 0 = Default (likely has your model)
- 1 = TransparentFX
- 2 = Ignore Raycast
- 4 = Water
- 5 = UI
- 8 = Post-Processing
- 9 = Throwable
- 10 = Droppable
- 11 = Ground
- 12 = Ragdoll
- 13 = Edible
- 14 = Mouth
- 15 = AvatarColliders
- 16 = World
- 17 = Prop
- 18 = OnlyAvatar
- 19 = Custom Object
- 20 = TransformGizmo
- 21 = Bubble
- 22 = Hidden on Main Camera
- 23 = Sticker
