# CS-330-11147-M01

**CS-330: Computational Graphics and Visualization — Final Project Portfolio**

This repository contains my final project artifacts for CS-330: the 3D scene
submission (`7-1_FinalProjectMilestones_James_Taylor_Final.zip`, source code +
Windows executable) and my Design Decisions document (`DesignDecisions.docx`).

The project recreates a 2D reference image of a corner desk setup as a
low-polygon 3D scene in C++/OpenGL: an L-shaped floating desk, hanging cubby
shelves, a triple monitor array, a 103-keycap keyboard with RGB underglow, a
trackball mouse, a boom microphone, and a soundbar — textured, lit with four
Phong light sources, and navigable with a free camera.

## Portfolio Reflection

### How do I approach designing software?

Working on this project taught me to design in layers. Before writing any code
I studied the reference image and decomposed every object into the basic
shapes available — a monitor became a base plate, a neck, a bezel, and a
screen face; a trackball became a box body, a sphere, a torus ring, and four
buttons. My design process was incremental and data-driven: I sketched the
room's coordinate layout first (floor spans, wall positions, desk height),
placed the largest objects to anchor the space, then worked inward to the
small desktop items. The most transferable tactic I developed is thinking of
objects as parameter lists (scale, rotation, position, material) rather than
unique geometry — that mindset made the scene table-driven and will apply to
any data-description problem, not just graphics.

### How do I approach developing programs?

Iteration was essential. Each milestone added one layer — geometry, then
camera interactivity, then textures, then lighting — and each layer forced me
to revisit and refactor the previous ones. My biggest new strategy was
extracting repetition into reusable abstractions: once I had hand-drawn a
dozen objects with the same transform-color-draw sequence, I created a
`SceneObject` class plus a single `RenderObject()` function, which collapsed
every draw into one readable call and made the 103-key keyboard a simple loop
over a data table. Across the milestones my approach shifted from "get it on
the screen" to "keep it maintainable": named constants instead of magic
strings, error-checked resource loading with graceful fallbacks, and comments
explaining the why behind each transform. Feedback from earlier submissions —
like checking texture-load return values — directly shaped the final code.

### How can computer science help me in reaching my goals?

This course gave me a working mental model of the graphics pipeline — how
vertex data becomes a frame through model/view/projection transforms, shaders,
and lighting math — which is foundational for any future work involving
visualization, simulation, or game development. Educationally, the linear
algebra and coordinate-geometry practice here transfers directly to other
fields like robotics, computer vision, and AR/VR. Professionally, building a
large feature across staged milestones mirrors real software delivery:
requirements decomposed into increments, refactored as they grew, and shipped
as a working executable. Debugging shader output, managing GPU resources, and
writing code another person can read are skills that carry into every
engineering role, graphics-specific or not.
