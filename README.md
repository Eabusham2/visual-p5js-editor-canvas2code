# visual-p5js-editor-canvas2code
made by Eabusham2 with Claude Opus 5, Claude Opus 4.6, Claude Sonnet 4.6, Cursor Composer 1.5, ChatGPT Codex, and Google Gemini Pro 3.1 High

desc: Shape Designer → p5.js is a single self-contained HTML file: no build step, no dependencies, no server. Draw on the canvas and it writes the p5.js sketch that reproduces it, live.


by Eabusham2
please star ❤️
feel free to make edits and push commits!!
if u want a feature/change ask in issues i may just do it 😏 

features: Basics
Shape Designer is a visual editor that generates live p5.js code. Draw shapes on the canvas and see the equivalent JavaScript update in real time below.

Toolbar (top): drawing tools, default colors, canvas size, grid, and export options.
Sidebar (right): properties for the selected shape, layer list, and template images.
Select (V): click to select, drag to move, drag outline handles to resize. Hold V for temporary Select from any tool.
Pan (H): drag to pan, scroll to zoom. Hold H or Alt for temporary Pan.
Undo/Redo: Ctrl+Z / Ctrl+Y or Ctrl+Shift+Z. On a Mac these are shown and work as ⌘. Turn on the History panel to jump several steps at once.
Click a shape twice within 5 seconds (when not on Select or Pan) to switch to that shape's tool — a double-click works too, but the clicks can be slow and far apart.
Multi-select: with Select, drag on empty canvas to rubber-band, or Shift/Ctrl+click objects to add and remove them.
Freehand (F): sketch a stroke; crossing your own line turns that loop into a smooth shape.
Right-click any tool or button to jump to its section in this guide.
Canvas
Central drawing area. Size is set by W and H in the toolbar. With a shape tool, double-click to open the Add Shape dialog for precise dimensions, position, and fill color; single click selects the shape underneath. Drag to draw with the current toolbar defaults — the point you press stays pinned as a corner of the new shape and only the edges you push out move, so nothing drifts under the cursor while snapping. The shape preview on the canvas behind the dialog stays at 50% opacity until you click Add to confirm. With Select, drag the body to move; drag outline edges or corners to resize; drag the rotate handle above the shape or the outside corner arcs to rotate; drag on empty canvas to rubber-band several objects at once.

Toolbar
Left: tool buttons (Select, Lasso, Eyedropper, Pan, Rect, Square, Ellipse, Circle, Arc, Triangle, Quad, Line, Arrow, Polygon, Star, Pen, Line Pen, Brush, Freehand, Pixel, Text, Vertical Text, Point, Shape Builder, 3D, and three DOM buttons — text field, type box, button). Shift+click a shape tool to open the Add Shape dialog with the shape centered on the canvas. Defaults: Fill, Stroke, Stroke weight; ∅ toggles for no fill/no stroke. Master opacity affects all shapes. Tool options: sides (polygon/star), arc angles, brush size/shape, freehand smoothing, font. Canvas: W, H, BG color. Options: Outline pad, Box0 (pad-0 bounds box), Snap (edges, grid, and equal spacing/margins), Pts, Prop (proportional resize), Click-switch, History panel, 3D mode, Move, Grid (size + subdivisions), Rulers, Unit, Pan (L/R/Shift), Theme (scheme, accent, Dark/Light/Auto, Frost), Lang. Per-tool options appear next to them as you switch tools: polygon sides, star points, arc angles, brush size, freehand smoothing, font, arrow Snap°/Thick%, shape-builder Smooth, 3D primitive/Depth/rX/rY, and DOM Hint/Style. Each toolbar group wraps its own contents when space runs short, so a wide group no longer drops to the next row whole and leaves a gap behind it. Right: Undo, Redo, Clear, Reset, Export PNG, Import Image, Export/Import Save, GitHub, About (i), Help (?).

Sidebar
Properties: when a shape is selected, edit type, position (X/Y), size (W/H or D), fill, stroke, dash, opacity, rotation, and type-specific fields. Click the Fill or Stroke color swatch to open the custom color picker. Layers: drag to reorder, click to select, lock/hide/rename. Folder support for grouping. Guides and History panels appear above Properties when they are switched on. Templates: reference images with opacity and show/hide for tracing. With none loaded the panel collapses to its header — just the master opacity and a + Add button — and drops to the bottom of the sidebar so it is not holding an empty strip open; it moves back into its usual slot between Properties and Layers as soon as an image is imported. The button across the top of the sidebar resets the sidebar width and the panel heights together.

Panels
Code panel (bottom): live p5.js code; noLoop, Hide defaults, Comments, Output (Sketch or Array), push/pop (Auto / Always / Never) and — in a non-English interface — the Code lang cycler; Copy and Download JS. Hide defaults now means "do not repeat a fill, stroke or weight that is already in effect", which is safe: a call is only skipped when it matches what the sketch has actually set, never merely because it matches this editor's own defaults. Color panel: opens from Fill/Stroke swatches or toolbar color inputs. Full custom picker with hue wheel, saturation/value box, RGB/HSL/HSB/CMYK/LAB tabs, hex input, swatches, and web colors.

Color Picker
Switch Fill or Stroke at top. Use the hue wheel and saturation/value box for intuitive picking, or RGB/HSL/HSB/CMYK/LAB sliders for precise values. Enter hex codes directly. Swatches save colors for reuse. Web colors grid for quick presets. Apply sets the current shape or the default for new shapes. Add Shape dialog: Click the Fill swatch to open the full custom color picker and choose a color before adding the shape.

Rulers, Guides & Units
Rulers (toolbar checkbox) run along the canvas and are labelled in the current unit. The dropdowns beside the checkbox move the horizontal ruler to the top or bottom and the vertical one to the left or right. The artboard span is shaded on each ruler, 0 and the far edge are marked in purple, and a cyan tick tracks the cursor.

Guides: drag out of either ruler to drop a guide, then drag it again on the canvas to move it. Guides snap to shape edges and centres, the canvas bounds, other guides and the grid, and shapes snap to guides in turn. Drag a guide off the artboard to delete it, or click the corner box where the rulers meet to clear them all. The Guides panel in the sidebar lists every guide with an editable position (in the current unit, with the pixel value beside it), plus +H, +V and Clear buttons. Guides are saved with the project and never appear in exported PNGs or generated code.

Units: choose px, pt, in or cm. Physical units reveal a PPI box (labelled PPCM for centimetres) with 72, 96, 150 and 300 presets — 72 is the default. Units drive the rulers, guide positions and the position/size readouts, and those readouts show the pixel equivalent in brackets. Font size and stroke weight stay in pixels on purpose: they are pixel values in the generated p5 code. Double-click a ruler to cycle units quickly.

Zoom
Zoom HUD (top-left of canvas): − / 100% / +, Fit, 100%, Center. Ctrl+scroll or pinch on canvas to zoom. Position label (top-right) shows cursor or selected center.

Select (V)
Click a shape to select it. Drag the body to move. Drag outline edge handles to resize; drag corner handles for width/height. Resizing pins the handle opposite the one you grabbed, so the far edge stays put instead of the shape drifting — hold Alt (or Ctrl) to scale from the centre instead, as in Illustrator. A side handle changes only its own axis; the Prop option applies to corner handles, and Shift is what makes a side drag proportional. Grabbing any handle or anchor keeps the offset you grabbed it at, so nothing jumps under the cursor when you press. On a rotated object the selection box turns with it and stays wrapped around the artwork, with the eight handles on its own corners and edges rather than on a level box drawn around the outside; the faint level box behind it is the object's screen-aligned extent, which is what snapping and the rubber band use. Drag the rotate handle above the shape or the small corner arcs outside the outline to rotate. While you turn, the badge reads out the angle and, in brackets, how far you have moved from where you started. V works both ways: tap it to switch to Select for good, or hold it from any other tool for temporary Select. Click a shape twice within 5 seconds (when not on Select/Pan) to switch to that shape's tool — the two clicks do not have to be a fast double-click. Bezier paths switch to Pen, straight-vertex paths to Line Pen. Locked layers show an amber outline.

Alt-drag a shape to duplicate it. The original stays exactly where it was and the copy comes away under the cursor, as in Illustrator; with several objects selected the whole selection is copied, and the copies end up selected so you can keep going. Alt still pans everywhere it is not over artwork, and under every drawing tool.

Escape cancels whatever you are dragging. Part-way through drawing, moving, resizing, rotating or pulling an anchor point, press Esc and the artwork goes straight back to how it was before you pressed the mouse — the abandoned move is not added to the history, so it costs you nothing and does not need undoing afterwards. With nothing being dragged, Esc deselects as before.

Selecting several objects: with Select active, drag on empty canvas to draw a rubber-band box — every object it touches is selected. Shift+click or Ctrl+click an object to add it to (or remove it from) the selection; hold the same key while dragging a box to add the box's contents to what is already selected. Dragging any selected object — by its body or its centre dot — moves the whole group, and Delete, the arrow keys, and the Del button all act on every selected object. The same Shift that adds an object also constrains a drag to one axis: press and drag rather than press and release, and the move locks to horizontal or vertical, whichever you have travelled furthest along. The key is read as you go, so you can reach for it part-way through a drag and let go again to free the other axis, and snapping will not pull the locked axis off. The last object you picked stays the primary: it keeps the resize and rotate handles, and the Properties panel shows its values (with a +N more hint). Hidden and locked layers are skipped. Esc or a click on empty canvas clears the selection. If Pan: Shift is enabled, Shift+drag pans instead, so use Ctrl+click to multi-select.

Click-switch (toolbar option): when on, a single click on any object instantly switches selection. When off, the first click deselects and a second click selects — useful to avoid accidental selection switches.

Move toggle (toolbar): when enabled, clicking an existing object with any draw tool selects and drags it instead of drawing a new shape. Clicking empty canvas still draws normally.

Eyedropper (I)
Copies appearance between shapes — fill, stroke, stroke weight, dash, opacity and gradient. Position, size and shape type are never touched, so you can paint a rectangle with a star’s look and it stays a rectangle. Between two text shapes the font, size, leading, alignment and letter angle come along as well; onto anything else they are left behind.

Select the shape you want to change first, then pick up the Eyedropper and click the shape whose look you want. With several objects selected, one click paints all of them. Hold Alt to run it the other way round — the selected shape’s appearance is pushed onto whatever you click, so you can style a run of shapes without reselecting between each one.

With nothing selected, clicking a shape loads its fill, stroke and weight into the toolbar defaults instead, so the next shape you draw comes out matching. Clicking empty canvas does nothing at all: losing the shape you were about to paint would be the opposite of helpful. Every use is a single undo step.

Pan (H)
Drag on the canvas to pan; scroll to zoom. H works both ways: tap it to switch to Pan for good, or hold it (or Alt) from any tool for temporary Pan and let go to return to what you were using. Right-click drag can also pan if enabled in options.

Adding shapes
Double-click on the canvas with a shape tool to open the Add Shape dialog—a translucent, see-through panel so you can view the canvas behind it. All existing shapes dim to 50% and the preview of the new shape appears at 50% of its Opacity slider value so you can see placement on the canvas. Shift+click a shape tool button, or hold a shape hotkey (R, S, E, C, T, A, P) for 3 seconds, to open the dialog with the shape centered on the canvas. When the dialog is open, clicking outside: single click does nothing; double-click cancels; triple-click confirms. Set X, Y position (editable). Choose Fill color with the inline color picker or advanced button. Drag the shape in the mini preview to reposition it; X and Y update live. Adjust dimensions (W, H, D, R, Rnd, Sides, Pts, In%, S°, E°) with number inputs and sliders. If you drag past a small distance, the shape is created by drag instead. Hover field labels for tooltips. Polygon and Star have preset buttons for quick ratios.

Rectangle (R)
Double-click to add (opens dialog with X, Y, W, H, Rnd, Fill); or drag to draw. The Prop checkbox in the toolbar decides what a drag does: with it on — which is the default — a plain drag comes out square and Shift frees the ratio, and with it off a plain drag is free and Shift makes it square. The same rule covers Ellipse, Arc, Triangle, Polygon and Star; Quad and the DOM controls are never constrained, since neither is square by nature. Set corner radius (Rnd) in the dialog or in properties. Use 4:3, 16:9, φ ratio buttons in properties for aspect presets.

Square (S)
Double-click to add (opens dialog); or drag to draw. Width and height stay equal. Use properties to resize. Corner radius in dialog or properties.

Ellipse (E)
Double-click to add (opens dialog); or drag to draw. Width and height are independent, but the Prop rule from Rectangle applies: with Prop on a plain drag gives you a circle and Shift lets the two axes differ. Resize via outline or properties. 4:3, 16:9, φ ratio buttons in properties.

Circle (C)
Double-click to add (opens dialog with center X, Y and diameter); or drag to draw by diameter. Diameter is editable in properties.

Triangle (T)
Double-click to add (opens dialog); or drag to create. In Select mode, drag the vertex points to reshape. Lock and link in properties for equal W/H. 4:3, 16:9, φ ratio buttons available.

Line (L)
Click for first point, drag to second, release. Two-point line only. Stroke color and weight apply.

Arc (A)
Double-click to add (opens dialog with angles and mode); or drag to draw. Set start and end angle (S°, E°) and mode (PIE/CHORD/OPEN) in the toolbar or dialog. Edit in properties.

Point (.)
Click to place a single point. Size is the stroke weight. No fill; stroke color applies.

Polygon (P)
Double-click to add (opens dialog for sides and radius); or set sides (3–30) in toolbar and drag to create. Preset buttons (△3, □4, ⬠5, ⬡6, ⬡8) in dialog. Resize via outline or properties; lock for equal W/H.

Star (*)
Double-click to add (opens dialog for points, inner %, radius); or set points and inner % in toolbar and drag to create. Preset buttons (★5, ★6, ★4, ★8) in dialog. Resize and lock like polygon.

Bezier Pen (N)
Click to add points; drag after a click to create curved (Bezier) segments. Click the first point again to close the path. Double-click on a segment to insert a new point — inserting is blocked if the click is within 12px of an existing node. Clicking near an existing point toggles it between hard (corner) and soft (smooth) without adding a new point. Paths can be closed in properties.

Line Pen (K)
Click to add straight segments. Click the first point to close, or double-click to finish an open path. New points are blocked if they would land within 12px of an existing node to prevent duplicate overlapping points.

Brush (B)
Freehand draw with circle or square stamps. Set size and shape in toolbar. Stroke is disabled; fill is used. 4:3, 16:9, φ ratio buttons in properties.

Freehand Shape (F)
Draw freely with the mouse held down. The moment the stroke crosses itself, the loop that just closed becomes a smooth closed bezier shape and everything drawn before it is dropped. Keep drawing and each further crossing makes another shape. A stroke that never crosses itself is kept as an open freehand curve instead, so the tool doubles as a plain sketching pen.

Smooth (toolbar): 0 keeps every wobble and joins points with straight corners; higher values average the hand jitter out of the run before simplifying it, so the curve follows the line you meant to draw rather than wandering through the noise, and corners you actually drew are kept sharp. While drawing, the faint dashed line is your raw stroke and the solid line previews the result through the same pipeline, so the preview is not a different curve from what you get. Esc cancels the stroke in progress. The result is an ordinary bezier path — editable point by point, and exported as p5 vertex/bezierVertex calls.

Pixel (X)
Paint grid cells on the canvas. Left-click to paint with current fill; right-click to erase. Grid size follows the grid option. First click selects or creates a pixel layer.

Text (W)
Click to place; drag to set initial size. Double-click to edit text; Shift+Enter for new line, Enter/Esc to confirm. Change font, size, alignment, leading, letter angle in properties.

Vertical Text (Shift+W)
Same as Text; letters stack vertically. Adjust angle and spacing in properties. Double-click to edit.

Selecting text works as you would expect: drag, double-click a letter, or hold Shift with the arrow keys, and the highlight is painted on the canvas behind the actual stacked glyphs — one cell per selected character, tilted to follow the column angle. The caret is drawn perpendicular to the column between characters and along it at the ends.

Undo
Revert the last action. Shortcut: Ctrl+Z (Cmd+Z on Mac). Supports multiple undo levels.

Redo
Reapply after Undo. Shortcut: Ctrl+Y or Ctrl+Shift+Z (⌘ on Mac, where every shortcut in this guide shows the Mac symbols automatically). See also the History panel for jumping several steps at once.

Clear
Remove all shapes and template images. Asks for confirmation. Does not reset options.

Reset
Clear all shapes and images and reset all options to defaults. Resets first-use pulsate on i and ?. Asks for confirmation.

Export PNG
Download the canvas as a PNG image at current view size and zoom.

Import Image
Add a reference image as a template layer for tracing. Adjust opacity and size. Toggle visibility with the eye button.

Export Save
Download the project as JSON to open later. Includes shapes, layers, templates, and options.

Import Save
Load a previously exported JSON project. Merges or replaces depending on context.

Help (?)
Opens this guide. Right-click any tool or button to jump to its section. Use Escape to close.

Lasso Select (Q)
Draw a freehand loop around the objects you want. The loop closes itself when you let go, and everything it encloses is selected. Shift or Ctrl while starting the loop adds to the current selection instead of replacing it. Hold Alt to select only objects that sit entirely inside the loop — without it, anything the loop touches is caught. Hidden and locked layers are skipped, and in isolation mode only the isolated shapes can be picked up. Esc abandons a loop in progress.

Arrow (G)
Press where the tail goes and drag to where the point should land — the cursor is the arrow tip the whole way, at any angle. Snap° in the toolbar snaps that angle to a set increment (15° by default; 0 turns snapping off) and holding Shift gives a free angle, the same way the Prop option inverts with Shift. Thick% sets thickness as a percentage of length. The badge shows length and angle while you drag.

In Properties, Head is the head length as a fraction of the width, Shaft is the bar thickness as a fraction of the height, Double puts a head on both ends and Flip reverses it. Clicking an arrow hits the arrow itself rather than its bounding box, so the empty corners no longer steal clicks from whatever is underneath. It exports as a beginShape() / vertex() / endShape(CLOSE) polygon with the drag angle emitted as a rotate(), so no extra p5 library is needed.

Shape Builder (Shift+B)
Illustrator-style combining. Pick the tool and drag a line across two or more shapes: every shape the line passes through is merged into a single bezier path. Hold Alt, or drag with the right mouse button, and the shapes the line crosses are instead cut out of the first one it touched. The stroke is green for combine and red for subtract while you drag.

Pathfinder buttons appear in Properties whenever two or more shapes are selected:

Unite — one path around the outside of everything selected (combine paths).
Minus — the bottom shape with every shape above it cut out of it (delete shapes from overlaps).
Intersect — keeps only the region every selected shape shares (create shapes from overlaps).
Exclude — keeps the parts covered an odd number of times, so overlaps are punched out.
Merge — flattens the selection into one path per colour, dropping whatever is hidden behind the shapes above it.
Every operation replaces the originals with bezier paths and is a single undo step. Line → Rect (Properties, when a line is selected) turns a line into a rotated rectangle whose height is its stroke weight, so it exports as rect() instead of line().

Smooth in the toolbar controls how closely the result follows the traced outline: 0 follows it exactly, higher is looser. Curves stay curves and corners stay square — a turn is hardened only when it is one its neighbours do not share, or when it is past 70° outright. A union of two rectangles therefore comes out with four sharp corners, while a union of two circles stays round to a fraction of a pixel. Comparing an actual union against the true outline, the fitted path is within about a quarter of a pixel on average.

The operations run on a rasterised copy of each shape, which is why ellipses, arcs, stars, text and brush strokes all combine correctly where analytic clipping would need a special case per type. Very thin slivers may be lost at extreme sizes; if that matters, scale up before combining.

3D primitives (3)
Drag to place a p5 WEBGL primitive: box, sphere, cylinder, cone or torus — chosen from the 3D dropdown that appears in the toolbar. The editor canvas is 2D, so each one is drawn as a light wireframe proxy showing footprint and depth; the generated sketch uses the real primitive.

As soon as one 3D shape exists, createCanvas() gains the WEBGL flag and draw() starts with translate(-width / 2, -height / 2), because WEBGL puts the origin at the centre of the canvas. Each primitive is then wrapped in its own push()/translate()/pop(). Depth in Properties is the Z size (a sphere ignores it — it only has a radius); a torus also gets a Tube radius. Delete the last 3D shape and the sketch goes back to a plain 2D canvas.

Moving it in 3D: rX, rY and rZ in Properties turn the primitive about each axis and become rotateX() / rotateY() / rotateZ() in the sketch; the toolbar carries rX/rY defaults for new primitives. Press Tumble in 3D and then drag anywhere on the canvas to spin it by hand — sideways turns about Y, up and down about X, two pixels of drag per degree. Esc or pressing the button again stops. Because the proxy is 2D it shows the pose as foreshortening plus a small red/green/blue axis cross rather than a true projection; the sketch does the real projection. This is separate from 3D mode, which fakes depth on ordinary 2D shapes.

DOM elements (D)
Three toolbar buttons sit side by side: Text field (⌨), Type box (▤) and Button (🔘). Drag to place one over the sketch. D picks the text field and Shift+D cycles through the three.

They are drawn here as flat mocks so you can position them against your artwork; the generated sketch creates the genuine element in setup() with createInput(), createElement('textarea') or createButton(), then calls .position() and .size() to match what you laid out.

In Properties, Value is the starting text (the caption for a button), Hint becomes a placeholder attribute, Cap is an optional label drawn above the control, and Style — plain, rounded, pill, dark — is emitted as .style() calls and drawn on the mock too, so the preview matches the page. A button also gets an onClick tick that writes an empty mousePressed() handler for you to fill in. The toolbar carries defaults for Hint and Style that every new control picks up. Naming a layer gives its variable a readable name in the generated code.

DOM · Type box
A multi-line textarea, created with createElement('textarea'). Everything in the DOM elements section applies — same Value, Hint, Cap and Style controls, same mock preview. Shift+D cycles to it.

DOM · Button
A clickable button, created with createButton(). Value is its caption. Tick onClick in Properties and the sketch gains an empty mousePressed(() => { }) block wired to it. Everything else matches the DOM elements section. Shift+D cycles to it.

Isolation mode
Double-click a shape with the Select tool to isolate it, or use the Isolate button in Properties. Everything else drops to 22% opacity and stops responding — clicks, rubber-band, lasso and snapping all ignore it — so you can work on one object in a crowded drawing without catching its neighbours. If the shape lives in a layer folder, the whole folder is isolated together.

A badge across the top of the canvas shows what is isolated. Click the badge, press Esc, double-click empty canvas, or press the Properties button again to leave. Undo and redo leave isolation automatically. Isolation is a view state — it never changes your artwork or the generated code.

History panel
Tick History in the toolbar options to show it in the sidebar. Every undo step is listed newest-first with a short label of what it was — Unite, Merge, Line → Rect, Edit and so on. Click any row to jump straight to that point: rows above Current are steps you can still redo (shown dimmed), rows below are steps to undo. Clear forgets the history without touching the artwork. The list holds the last 50 steps, the same limit undo has always had.

Interface themes
The Theme group in the toolbar restyles the app itself — Midnight, Slate, Carbon, Forest, Rose, Ocean and Custom. The colour swatch beside it sets the accent; picking one switches the scheme to Custom. The Dark / Light / Auto dropdown inverts the interface between dark and light surfaces, keeping the accent; Auto is the default and follows your system appearance, switching live if you change it while the page is open. Frost makes panels, popups and tooltips translucent with a frosted blur. Small controls such as the ▲▼ steppers and the mini buttons take their own surface colour from the theme, kept deliberately distinct from the panel behind them so they stay readable in every scheme.

Themes deliberately touch only the interface. Canvas background, grid colour and every shape colour are your document, not chrome, so they never change with the theme — what you export looks the same whichever theme you work in. The theme is saved with the project.

3D mode & extrusion
Tick 3D in the toolbar options and every new shape is drawn as a stack of offset, darkening copies, so it reads as extruded. Any shape already on the canvas can be given the same treatment with the 3D tick at the bottom of Properties — including text, which is how you get chunky extruded lettering.

It is deliberately dumb 3D: the same shape drawn several times, each copy nudged a little further along one direction and shaded darker. That means it needs no WEBGL, works on every shape type, and the generated p5 is a plain for loop with a lerpColor() — code you could have written yourself. Controls: Depth (how far back the stack runs), Dir° (which way), Steps (how many copies — more is smoother and slower), Shade (how much darker the far end is) and In front (stack toward the viewer instead of away).

The selection outline stays on the base shape, not the extrusion, so resizing and positioning behave exactly as they did before. This is unrelated to the 3D primitives tool, which uses a real WEBGL canvas.

Language
The Lang dropdown in the toolbar sets the interface language: English, Español, Français, Deutsch, Português, 日本語 or 简体中文, plus Auto (the default), which follows your device. Anything without a translation stays in English rather than showing a blank or a raw key, and abbreviations that are really symbols (W, H, BG, Op, rX) and p5 API words (RGB, DEG, box, sphere) are left alone on purpose so they still match the generated code. Tooltips and this guide are English only.

When the language is not English, a Code lang cycler appears above the code panel with three states. Off leaves the sketch entirely in English. Comments only translates the comments this editor writes. Everything also renames the variables the editor invents, such as the DOM element handles. p5.js function names are never translated in any state — there is no localised p5, so rect() is always rect() — and a name with no translation keeps its English form rather than coming out half-renamed.

Code output modes
Output in the code panel header switches between two shapes of output:

Sketch — the normal full p5 sketch with setup(), draw(), background() and the rest.
Array — no setup(), no draw(), no background() and no noLoop(). You get the mode calls (angleMode(), and colorMode() when it is not RGB) followed by one big const SHAPES = [ … ] array holding every shape as plain data — type, geometry, fill, stroke, weight, alpha, rotation. Drop it into a sketch you already have and loop over it yourself. Placement, noLoop and Hide defaults are greyed out in this mode because they have nothing to act on.
push/pop controls the wrapping around each shape: Auto emits push()/pop() only when a shape needs it (rotation, opacity, gradient or dash), Always wraps every shape so nothing can leak state, and Never omits it entirely for the shortest possible code.

textWidth(): tick use textWidth() on a text shape and its code lays the text out with textAlign(LEFT, …) plus text(str, x - textWidth(str) / 2, y) instead of letting textAlign do the centring — handy when you want the measurement available in your own sketch. Multi-line text becomes a lines[] array with a for loop. The TW readout in Properties always shows the measured width of the widest line, the same number p5 would return.

Advanced Tips
Add Shape dialog: Double-click canvas, Shift+click shape tool, or hold shape hotkey 3 sec to open. Existing shapes dim to 50% and the preview appears at 50% of its final opacity so you can see placement. Opacity slider sets the final shape opacity and the canvas preview follows it. The Rotate slider (with a number box you can double-click to reset) spins the shape before you add it. Click outside: double-click=cancel, triple-click=confirm. Translucent panel; inline color picker always renders on top; drag shape in mini preview to reposition.
Click-switch: When on (default), single-clicking any object instantly switches selection. When off, first click deselects, second click selects — useful to avoid accidental switches while drawing.
Move toggle: Enables clicking existing objects with draw tools to select and drag them instead of creating new shapes. Empty canvas still draws normally.
Anchored drawing: While dragging out a new shape the mouse-down point is locked as a corner. Only the edges you are pushing out snap, exactly like a resize handle, and the shape under construction is excluded from its own snap targets — so circles, squares, triangles, stars and arcs no longer creep away from where you started them.
45° guides: Alongside the vertical and horizontal guides, a cyan diagonal appears when a moving object lines up at 45° with another object's centre, the canvas centre, or a canvas corner. Hold Shift with Line, Line Pen, or Pen to lock the segment to 45° increments and see the same guide.
Grid subdivisions: Adobe-style. Sz sets the spacing of the main gridlines and Sub splits each cell into that many fainter divisions, which also become snap targets.
Visual CMYK: the CMYK checkbox next to the code colour mode switches every colour readout in the interface to C/M/Y/K, including a fourth sidebar slider. It is display only — p5 has no CMYK mode, so the generated code keeps using the RGB/HSL/HSB/LAB mode selected beside it.
Aspect presets: 4:3, 16:10, 16:9 and φ buttons in Properties set height from width for rectangles, ellipses, arcs, polygons, stars, triangles, quads, paths and brush strokes.
Snap: When on, resize and move snap to grid lines and shape edges. Rects snap to edge+outline; stars/polygons/triangles snap to outline only.
Spacing & margin snap: While moving an object, it also snaps so the gap it leaves matches a gap that already exists between other objects in the same row or column, or so it sits centred between two neighbours with equal gaps on both sides. The canvas borders count as neighbours, so an object also snaps to equal margins from the canvas edge (which centres it). Pink measurement bars label the matched gap in pixels. Turn it off with the Snap checkbox.
Multi-select: Drag on empty canvas with Select to rubber-band; Shift/Ctrl+click to add or remove one object; Shift/Ctrl+click in the Layers list works too. Dragging moves the whole group and Delete removes all of it. The primary (last-picked) object keeps the resize/rotate handles.
Two-click tool switch: Clicking the same object twice within 5 seconds switches to that object's tool, unless you are on Select or Pan. Handy for matching an existing shape without hunting the toolbar.
Outline pad / Per-type: Pad controls the gap between a shape and its selection outline. Enable Per-type to store a separate pad per shape type — select a shape and adjust its pad individually.
Clip to canvas: Toggle in toolbar. When off (default), shapes outside canvas are visible. When on, shapes are clipped to canvas bounds in the generated code.
Gradients: Enable Grad in properties for fill; add stops, set angle/radius. Swatches can link shapes to shared colors.
Layer folders: Create folders to group layers. Drag layers into folders. Lock/hide per layer.
Code options: noLoop for static sketches; Hide defaults omits redundant fill/stroke; Comments adds explanatory notes.
Proportional resize: Prop option makes resize preserve aspect ratio by default. Shift during drag toggles.
Pad-0 box: the Box0 option draws a hairline grey rectangle flush against a shape's real bounds whenever it is hovered, selected or being modified. The normal outline sits at the Pad distance, so this is the one that shows true extents.
Grid line-up: with a draw tool armed and both Grid and Snap on, a small purple cross marks the grid intersection your next click will actually snap to, so the cursor and the grid agree before you commit.
Steppers: the ▲▼ arrows next to the canvas size, the text fields and every Add Shape number box share one style and one behaviour — click to step by the field's own increment, hold Shift to step by ten.
Tooltips: hovering anything with a tooltip shows it after a short, consistent delay instead of waiting on the browser's slow native title popup, and toolbar tooltips appear instantly with no fade-in.
Mac keys: on macOS every shortcut in tooltips and this guide is relabelled ⌘ / ⌥ / ⇧. Both Ctrl and Cmd have always worked; only the labels change.
Shape Builder: drag across shapes to combine them, Alt or right-drag to subtract, or use the Unite / Minus / Intersect / Exclude / Merge buttons that appear in Properties with 2+ shapes selected. Results are bezier paths in one undo step.
Isolation mode: double-click a shape with Select (or press Isolate in Properties) to dim and disable everything else. Esc leaves.
3D and DOM: 3D primitives switch the sketch to a WEBGL canvas; DOM elements are created in setup() with createInput()/createElement()/createButton(). Both are drawn as proxies in the editor.
Selection persistence: Selected shape and template image are saved with the project; restored on load, export, and return.
Resize anchoring: the handle opposite the one you grab stays pinned, so the shape does not drift while you resize. Alt (or Ctrl) scales from the centre instead. Side handles change one axis only — Prop applies to corners, and Shift is what makes a side drag proportional.
Grab offset: handles and anchor points move by the same delta as the mouse instead of jumping under the cursor the instant you press, so a slightly-off grab does not nudge the shape.
Tiny shapes: on a shape small enough that all its handles overlap, clicking inside it picks the centre dot (which moves it) and clicking at or outside an edge picks the corner or side handle, rather than whichever happened to be a pixel closer.
Centre dot everywhere: the centre dot can be grabbed to move a shape with the Brush, Freehand, Pixel and Line tools too, not only the drawing tools that already allowed it.
Arrow tip: the Arrow tool puts the tip under the cursor and snaps the angle to the Snap° increment; hold Shift for a free angle. Arrows are selected by their actual outline, not their bounding box.
3D mode: the 3D option arms fake extrusion on everything you draw next, and any shape (text included) can be extruded from the 3D tick in Properties. It exports as a readable for loop, no WEBGL needed.
Tumble: a WEBGL primitive can be spun by hand — press Tumble in 3D in Properties, then drag anywhere on the canvas.
Random colour: the 🎲 in the colour picker gives a usable vivid colour; Shift+click for raw random RGB, Alt+click to keep the hue and reroll only saturation and value.
Language: the interface follows your device by default and falls back to English string by string. In a non-English interface, the Code lang cycler above the code panel translates the generated comments, and optionally the variable names this editor invents — never p5 function names.
Output fidelity: the generated sketch is checked against the editor canvas pixel by pixel. A fill or stroke call is skipped only when the sketch has already set that exact value, so a white shape after a red one keeps its white, and closed bezier paths emit the curve that closes them rather than a straight line.
