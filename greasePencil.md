# Grease Pencil

## Grease Pencil Fundamentals

[Grease Pencil Fundamentals](https://studio.blender.org/training/grease-pencil-fundamentals/)>

### v02-The New GPencil Object

Grease pencil is an object in Blender that stores LocRotSca, parenting and display from 3D World, and have the modes:

- Object
- Edit
- Sculpt
- Draw
- Weight Paint

Its object data stores:

- Strokes and Fills
- Layers
- Vertex Groups

Object data can be share with objects and data's stroke are make of +2 point linked on a path are store on a layers.\
Material had the color and feels of the brush.

### v03-Object Mode

Adding a grease pencil create an empty object with a distinguish square on it (just a point in v3.4.1) that holds object data on it. For precision, use Sidebar > Transform Panel (N) or Properties Editor > Object Tab > Transform Panel.

Shift-D: Duplicate Object.\
Alt-D: Duplicate Link.\
Duplicate Link shares data object between objects, making them an instance with is own LocRotSca.\
Ctrl-P(with +1 object selected): Parent Objects\
The last selected object will be the parent that pass on his LocRotSca from now to their child\

On Outline Editor, you can CRUD object inside a Collection to organize them in groups\
Object mode have it own Overlay for the 3D Viewport, like:

- Onion Skin: Shows frames before and after of a object in the actual frame
- Canvas: shows grid used as plane for the drawing and can be edited on Properties Editor > Data Object Tab > Viewport Display Panel > Canvas Sub-panel
- Fade 3D Objects: Fade Depth and 3D object, leaving only Grease Pencil visible (Fade Inactive Object in 3.4.1)
- Properties Editor > Data Object Tab > Viewport Display Panel >:
  - Depth Ordering: Makes drawing appears in front/behind/at the 3D position related to 3D objects (Is inside Strokes in 3.4.1)
  - Marker Size: Resize Grease Pencil Empty for visibility (Does not exist in 3.4.1)
  - Thickness Scale: Resize line thickness for Viewport
    - Keep Thickness: Lock Thickness Scale (Does not exist in 3.4.1)

### v04-2D Animation Template

Blender 2.8+ have new template for 2D animation that have the workpaces:

- 2D Animation: Default use of 2D animation and is in Draw Mode with layers tab (Layers tab is not set in 3.4.1)
  - Properties > Modifier Tab and Effect Tab add non-destructive effect on your work
  - Come with dopesheet to help you animate
  - Animation Editor have just the usufull command visible
- 2D Full Canvas: Only have 2DViewport, Dopesheet and Timeline Editor
- Compositing: Use Node system do edit your render (This exist in 3.4.1)
- Rendering: View work after rendering

### v05-Drawing mode

Set the Pen lower button as MMB to move on scene and upper as RMB for selection/menu.\
Ctrl-LMB (Drag in Draw Mode): Eraser.\
In 3D Viewport Editor > Overlay menu > fade layers, makes not selected layers more transparent.\
In Properties Editor > Layers Tab, you can lock other layers manually or automatically (via Down arrow button) to avoid mess with other layers.\
On Pen Settings (Above the 3D Viewport Editor) > Option Menu, you can activate/edit the Stabilizer for a smooth draw.\
Shift-LMB (Drag in Draw Mode): Draw with stabilizer.\
At Tool Panel, you have Primitives to draw fixed form and confirm with Enter/MMB.\
E: Draw line per anchor point.\
In Upper part, activate Thickness profile to change brush thickness. Use Fill tool in another layer (below the lineart), to fill a area with a color.\
Alt-LMB: Draw temporary limit for fill tool.\
Ctrl-LMB: Manually draw fill area (Ctrl inverse fill, Shift is it in 3.4.1).

### v06-Editing Drawings - Edit & Sculpt mode

Tab: Toggle Draw/Edit mode.\
1(In Edit Mode): Edit by point.\
2(In Edit Mode): Edit by line.\

You can select, group, transform like other object, but you can also use Bend, Shear and use Sphere tool. Grease Pencil’s Edit mode have more tools like Smear or Shear.\
In Overlay Menu, you can toggle to view Edit Lines and Vertex Opacity.\
In Strokes Menu you can group, change layer, reorder strokes, delete loose points (delete loose points move to Grease Pencil Menu in 3.4.1).\
Strokes Menu > Clean up > Re-project Strokes flatten the 3D placement of strokes (Moved to Grease Pencil Menu in 3.4.1).

Sculpt Mode work in similar as sculpt for the 2D, here a list of tools:

- Smooth
- Thickness
- Strength: Edit Opacity
- Randomize: Jitter the line
- Grab
- Push
- Twist
- Pinch
- Clone: Copy a stroke in Edit mode and clone like a stamp

### v07-2D Animation

For quick animation:

- Set length on Timeline
- Draw movement line in camera view in a upper layer
- Lock the layer to avoid edit
- In a middle layer draw the object in frame 1
- Edit the draw using Edit/Sculpt if needed
- Add image/3D object as reference if needed
- Move a few frames a draw/move a new frame of the object
- After complete the animation, create a new layer and make the lineart for each frame

Object Data can edit Onion Skinning settings.\
Shift-D (In Timeline and with frames selected): Duplicate keyframe.\
X (...): Open Delete Menu.\
Del (...): Delete selected.\
3D Viewport Editor > Multiframe Button, let you edit selected frames at same time, which is good for reuse animation in different places or fill color in multiple frames.\
The idea is to:

- Make sketch on every wanted frame (Duplicate if needed)(Use 3D model if need a complex reference)
- Adjust the sketch with Edit e Sculp Mode
- Lineart using mode smooth strokes or line tools
- Color and shade with fill tool

### v08-Drawing Brushes and Materials

Pencil, Fill and Eraser Tool have their own brushes that can be edit in Properties Panel > Active Tool Tab or 3D Viewport Top bar.\
F: Edit brush radius.\
Shift-F: Edit brush Strength.\
You can select Brush, Layers on 3D Viewport, but CRUD them on Properties Editor. Brush material can have Stroke and/or Fill

Editing a material alters the done strokes.\
3D Viewport > Option Menu (in 4.2 is in ..Stroke menu), can refine your draw:

- Angle affect stroke thickness per angle
- Factor is how strong the angle will affect
- Post-processing affect the line when end the stroke
- Stabilizer Settings affect the smoothness of the line while drawing
- Random gives difference while drawing

Curves menu adjust the behavior per pressure.\
In Properties Panel > Material Tab > Surface Panel, its subpanel have Style, that let you select a texture based on a image, making complex brush materials; if a image is B/W and transparent, check Use As Pattern to make colorize it. The Fill Subpanel have Gradient and Checkerboard Style (Checkerboard was removed in 3.4.1)

### v09-Drawing and Layout in the 3D space

Stroke Placement select on where the drawing will be in 3D based on the selected placement. Stroke Option makes stroke beginning position based on a existing one, and the middle and end points can also follow depending of Target selection.\
Surface Option have Offset value field in case of drawing being clipped in surface.

Drawing Plane select if the drawing angle will be on a axes or on the current view.\
Overlay Menu > Canvas shows the grid use as plane of the drawing.\
Check Properties Panel > Camera Lock > Lock Camera to View to be easier to adjust camera to scene (In 3.4.1 is in Properties Panel > View Tab > View Panel > View Lock Subpanel).\
N: Properties Panel\
You can incorporate 2D, 3D and other objects on scene and draw 2D above the 3D. You can use Local View to see only the selected object adn edit it individually.\
/: Local View

### v10-Modifiers and VFX Shaders

In Properties Editor > Modifiers Tab, you find tools that edit the 2D object in a general and non-destructive way; they can be stacked (up to bottom), duplicated to get accumulate effect and applied to object to make the changes destructive and permanent. Tint Mod. can usefull for global light color over scene without need to recolor the objects or change lineart color (for lineart, it need to have layer for it).\

In VFX Tab there are tools to edit real time effects, but cannot be applied.#
Tip for easy shadow:

- Duplicate the caracters (it will inrerith animation)
- Rotate it to be on floor
- Add Tint Mod. for shadow color

Use Rim VFX for easy rim light.

To animate a non greae pencil object:

- Select the object
- In Dopesheet Editor > Dopesheey Mode, in the wanted frame, keyframe it
  - I: Keyframe Menu
- Move the timeline to another frame and keyframe it

### v11-Rendering and Compositing

*** In Blender Header Menu, isolate composition using Layers Menu:

- Create a new Layer
- In Outline Editor, RMB on Collection and click on View Layer > Disable from View Layer, to remove collection from layer
  - E: Disable from View Layer

For this example we use 3 layers image and a transparent background.\
Set Properties Editor > Render Tab > Film Panel > Alpha = Transparent. In Compositing Editor, Add a Render Layers Node for each Layer and set Scena as the layer.\
We will add Blur for layers except the character layer, Glare to Character layer to improve the rim light, and Color Balance to fix the color.\
Here is the composition:

```Plain text
RGB (with orange tone) > AlphaOver0.Image0
RenderLayers0.Scene = VL_Background
RenderLayers0.Image > Blur0.Image
Blur0.X = 13
Blur0.Y = 13
Blur0.ImageOut > AlphaOver0.Image1
RenderLayers1.Scene = VL_Character_Shadow
RenderLayers1.Image > Blur1.Image
Blur1.X = 9
Blur1.Y = 9
Blur1.ImageOut > AlphaOver1.Image1
RenderLayers2.Scene = VL_Character
RenderLayers2.Image > Glare.Image
Glare.Threshold = 13
Glare.Streaks = 3
Glare.AngleOffset = 45
Glare.ImageOut > AlphaOver2.Image1
AlphaOver0.ImageOut > AlphaOver1.Image0
AlphaOver1.ImageOut > AlphaOver2.Image0
AlphaOver2.ImageOut > ColorBalance.Image
ColorBalance.Gain = Light Orange
ColorBalance.ImageOut = Composite.Image
```

### v12-Annotate

In Object Mode, you have Annotate Tool to put non-rend notes inside the scene, it can also be used in others editors like Image or Compositor and alswith the tool selected you can change Color, Placement (In 3D Cursor, View or Surface).]
D-LMB(Drag): Annotate Tool

There are 4 type of Annontate Tool:

- Default: Freestyle anotation and also used with the shortcut
- Line: LMB(Hold) To make a new line
- Polygon: Make a line connecting the last unhold of LMB to another
  - Shift-Alt-D: Annotate Polygon
- Eraser: Erase vertices from the notes(Edits its size in the Upper Bar or with Scroll)
  - D-RMB(Drag): Eraser

Create layers and edit its setting in Upper Bar, part of the setting can also be edited in or Properties Panel > Annotations SubPanel (In 3.4.1 is in Properties Panel > Tool Tab).\
Hide annnotation per layers in the Notes Menu or as a whole in Overlays Menu > Annotations.\
Make notes per frame by selecting a wanted frame in Dopesheet Editor > Grease Pencil Mode (Dope Sheet Mode in 3.4.1), it is for animation.\
You can lock the a single frame note for the whole animation by checking Nodes Menu > Lock Frame,  usefull for passage or archs on animations.\
Delete the ealier frame by clicking on X on the same button.

## Blender 2D/3D for beginners, drawing and animating with greasepencil (v2.8)

[1](https://www.youtube.com/watch?v=c57qq2nE3B0), [2](https://www.youtube.com/watch?v=mhcNPYxPqhw)

For tablet user, Go to Preferences > Input > Mouse and check Enable 3 Button Mouse This make Alt-LMB to MMD

Dope sheet use object name (Orange color in Outline editor) and not mesh name (Green).\
Use 3D Object and Stroke Placement as Surface to draw in exact place, if you use Empties, you will need to go to Object Mode, select it and move 3D Cursor to it.\
In 3D Viewport editor > Advance Menu, set Input samples = 1 and Activate Smooth = 0.3.\
Change Canvas Orientation and move it base on origin to give depth ind perspective; when drawing on mesh surface, edit Offset to avoid clipping or floating and always draw in ortho axys.

Create layers for each object that had different keyframes/loops and another one for fill and lineart. Fill uses actual perspective and layers to fill the lineart. If the same layer is overlaping when using Fill Tool it will fill partailly and if a minor area is surrounded by a bigger one, the Fill will cover the minor with the bigger fill.\

Use Cube as canvas position reference and use then for floating drawings and place it a non-render collection.\
Use Sculp/Edit Mode to close the gap of the sides; verify the orientation, to avoid broke the line instead of fixing it.\
Set Properties Editor > Object Data > Stroke Panel > Stroke Depth Order to 3D Location to avoid seen through the object but it needs to move overlapping layers since it was based on 2D layers.

For 2D Straw drawing use a Empty and place on drawing collection, rename it even the object data.\
When use Fill Tool, use temporary strokes to fill a gap when use it.\
Alt-LMB: Temporary Stroke\
In Outline Editor, Shift-LMB(Drag) the straw into the box so it will be part of it.

When you rotate a object they reference plane goes too, for extra object just create a empry for it and a linear and fill layer.

Insert a keyframe in timeline to have a clear view of the drawing.\
Check Overlay Menu > Onion Skin to see before/after frames and check Properties Editor > Object Taba > Layers Panel > Layer Onion Skin, to activate it

## Blender Grease Pencil RANDOM tips & tricks

[Blender Grease Pencil RANDOM tips & tricks](https://www.youtube.com/playlist?list=PLvashLL2utJGz0yuPBU7gGn-smNT8A3JM)

### v004

Vextex paint do not use material as color but need a material do taint over it

### v005

Use material/layers as mask for vertex paint by locking unwanted ones\
Vertex Blur can mix colors

### v006

Locking brush also lock material linked to it

### v009

Y(In Draw mode): Layer menu

### v010

In Edit Mode, selected point can be move to another layer, even if is not the whole drawing
Alt-S: Edit Thickness

### v013

Alt-Z: X-ray
X-ray let you see overlapping draw, even on same plane

### v014

In Timeline E key extrude the selected frames on the side of mouse is from the Playhead
T: Slide the keyframes and keep time frame os the first/last keyframe, making animate faster/slower on wanted part\
Both found on **Frame Menu**

### v015

In Properties Editor > Object Data Tab > Layers Panel or in Materials Tab, you can click on arrow below the layers list to open a search bar\
Filter for more element by adding * (Ex: A*B)\
Click on button next to it, will invert the search

### v017

Use Pixel Effect with Thickness Mod. to look better

### v018

**Dope Sheet Editor > Layers Special Menu > Autolock Inative Layers**, can avoid edit wrong layer

### v020

Fake a 3D by cut a plane with knife tool and and animate it the border as a shape key
You can animate a camera along

### v022

With Lock Object Mode uncheck, use Properties Panel(N) to transform object without exiting Draw Mode

### v023

Use a static instance of a object to edit/draw on moving/clustered places

### v024

Use a Zoomed out inverse Fill tool with low precision and huge leak size to make a quick object background (Fill tool can be edit in upper part of 3D Viewport)

### v025

Draw with Auto-keyframe off only edit the actual frame, but with it on, it create a new empty keyframes on non-existante frame

### v026

In v3.4, Fill tool have an **Advance Menu > Gap Closure Panel > Mode**, with it, it show lines/radius from gap that help the Fill Tool\
Radius mode needs the radius to change into a line to close it\
PG Up/Down, Scroll or Pen MMB: Change Gap Closure lenght\
S: Gap Mode\
U: Material Menu\
Alt-LMB: Temporary Stroke (help with gaps)\
- **Draw Menu > Clean UP > Boundary Strokes**, will remove temporary strokes

### v027

In Sculpt Mode, you can auto mask by stroke\
Or, in Upper left of 3D Viewport, you can select a stroke but change to edit stroke\
Ctrl-Alt-RMB: Lasso Select\

### v028

In Upper left of 3D Viewport check Curve Editing to edit the draw as spline\
Subdivide to add archor point

### v031

Grease Pencil Tools Add-on make you:

- Ctrl-LMB(Drag): Move Keyframe
- Ctrl-Alt-MMB(Drag): Rotate canvas
- 1~4: Subdivide Lattice

In v3.5, Y: Layer Menu, can:

- Toggle
- Swap
- (Hover at the side): See layer
- (Drag sideways): Set opacity

### v030

In v3.4, Check Tool Menu > Stroke > Outline to have a brush vectorized by the border and used the set solid field material that can be used for Sculpt later.\
Properties Editor > Material > Surface > Fill > Style, it can place a texture for it.\
With a stoke selected, click on Stroke Menu > Outline to turn into a outline.
