# Manim

**Manim (Mathematical Animation Engine)** is a Python library for creating precise and beautiful mathematical animations.

It can be used to visualize:

* Mathematical equations
* Functions and graphs
* Geometry
* Linear algebra
* Calculus
* Probability
* Statistics
* Coordinate systems
* Algorithms
* Physics concepts
* Mathematical proofs

Manim is especially useful for creating **educational mathematical videos** because animations can be controlled programmatically.

---

## **`What is Manim?`**

Manim is a Python-based mathematical animation framework.

Instead of manually drawing every frame of a video, we describe mathematical objects and animations using Python code.

For example:

```python
from manim import *

class HelloWorld(Scene):

    def construct(self):
        text = Text("Hello, Manim!")

        self.play(Write(text))
        self.wait(2)
```

This creates a scene containing the text:

```text
Hello, Manim!
```

and animates it onto the screen.

---

## **`Why Learn Manim?`**

Manim is useful when you want to explain mathematical concepts visually.

For example, instead of simply writing:

```text
a² + b² = c²
```

we can create an animation showing:

```text
       c
      /|
     / |
    /  | b
   /   |
  /____|
     a
```

and visually demonstrate why:

```text
a² + b² = c²
```

This makes mathematical concepts easier to understand.

---

## **`Main Concepts of Manim`**

Manim is primarily built around three important concepts:

```text
Manim
 │
 ├── Mobject
 │
 ├── Animation
 │
 └── Scene
```

---

**`1. Mobject`**

**Mobject** stands for **Mathematical Object**.

Mobjects are the objects displayed in a Manim scene.

Examples include:

* `Circle`
* `Square`
* `Triangle`
* `Line`
* `Arrow`
* `Text`
* `MathTex`
* `Axes`
* `NumberPlane`
* `VGroup`

Example:

```python
from manim import *

class Shapes(Scene):

    def construct(self):

        circle = Circle()
        square = Square()

        self.add(circle, square)
        self.wait(2)
```

Here:

```text
Circle → Mobject
Square → Mobject
```

Manim's documentation describes Mobjects as the basic building blocks of animations.

---

**`2. Animation`**

An **Animation** defines how a Mobject changes over time.

Examples:

```python
Create()
Write()
FadeIn()
FadeOut()
Transform()
ReplacementTransform()
GrowArrow()
Rotate()
```

Example:

```python
from manim import *

class AnimationExample(Scene):

    def construct(self):

        circle = Circle()

        self.play(Create(circle))
        self.wait(2)
```

The `Create()` animation gradually draws the circle.

---

**`3. Scene`**

A **Scene** is the canvas where your animation takes place.

A typical Manim program creates a class that inherits from `Scene` and defines the animation inside the `construct()` method.

Example:

```python
from manim import *

class MyScene(Scene):

    def construct(self):

        circle = Circle()

        self.play(Create(circle))
        self.wait(2)
```

The structure is:

```text
Scene
 │
 └── construct()
       │
       ├── Create Mobjects
       ├── Add Mobjects
       └── Play Animations
```

---

## **`Installing Manim`**

Manim Community can be installed using Python's package manager.

First, create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```powershell
venv\Scripts\activate
```

Then install Manim:

```bash
pip install manim
```

Verify the installation:

```bash
manim --version
```

You can also check the installed version from Python:

```python
import manim

print(manim.__version__)
```

---

## **`Creating Your First Manim Project`**

A simple project structure can look like this:

```text
ManimProject/
│
├── scenes/
│   ├── hello.py
│   ├── geometry.py
│   └── algebra.py
│
├── media/
│
└── README.md
```

---

**`Your First Manim Animation`**

Create a file:

```text
hello.py
```

Add:

```python
from manim import *

class HelloManim(Scene):

    def construct(self):

        text = Text("Hello, Manim!")

        self.play(Write(text))
        self.wait(2)
```

Render it using:

```bash
manim -pql hello.py HelloManim
```

The general workflow is:

```text
Python Code
     ↓
Manim Scene
     ↓
Mobjects
     ↓
Animations
     ↓
Rendering
     ↓
Video
```

---

## **Understanding `self.play()`**

`self.play()` is used to play animations.

Example:

```python
self.play(Create(circle))
```

Multiple animations can also be played together:

```python
self.play(
    Create(circle),
    Write(text)
)
```

---

## `self.wait()`

`self.wait()` pauses the scene.

```python
self.wait(2)
```

This creates a 2-second pause.

Example:

```python
from manim import *

class Example(Scene):

    def construct(self):

        text = Text("Hello")

        self.play(Write(text))

        self.wait(2)

        self.play(FadeOut(text))
```

---

**`Basic Shapes`**

Manim provides many predefined geometric objects.

`Circle`

```python
circle = Circle()
```

`Square`

```python
square = Square()
```

`Rectangle`

```python
rectangle = Rectangle()
```

`Triangle`

```python
triangle = Triangle()
```

`Line`

```python
line = Line(LEFT, RIGHT)
```

`Arrow`

```python
arrow = Arrow(LEFT, RIGHT)
```

---

## **`Example: Basic Shapes`**

```python
from manim import *

class Shapes(Scene):

    def construct(self):

        circle = Circle()
        square = Square()
        triangle = Triangle()

        circle.shift(LEFT)
        square.shift(UP)
        triangle.shift(RIGHT)

        self.play(
            Create(circle),
            Create(square),
            Create(triangle)
        )

        self.wait(2)
```

Manim uses a coordinate system where the origin is at the center of the screen. Directions such as `UP`, `DOWN`, `LEFT`, and `RIGHT` can be used to position objects.

---

## **`Positioning Objects`**

Manim provides several methods for positioning Mobjects.

`shift()`

```python
circle.shift(RIGHT)
```

Move an object to the right.

`move_to()`

```python
circle.move_to(UP)
```

Move an object to a specific position.

`next_to()`

```python
square.next_to(circle, RIGHT)
```

Place the square next to the circle.

`align_to()`

```python
square.align_to(circle, UP)
```

Align objects relative to each other.

---

## **`Mathematical Text`**

One of the most powerful features of Manim is rendering mathematical equations.

Use:

```python
MathTex()
```

Example:

```python
from manim import *

class Equation(Scene):

    def construct(self):

        equation = MathTex("x^2 + y^2 = z^2")

        self.play(Write(equation))
        self.wait(2)
```

This is especially useful for:

* Algebra
* Calculus
* Linear Algebra
* Trigonometry
* Probability
* Statistics

---

## **`LaTeX in Manim`**

Manim uses LaTeX for mathematical typesetting.

Example:

```python
equation = MathTex(
    r"\frac{d}{dx}(x^2) = 2x"
)
```

Another example:

```python
equation = MathTex(
    r"\int_0^1 x^2\,dx = \frac{1}{3}"
)
```

---

## **`Text vs MathTex`**

Use `Text` for normal text:

```python
Text("Linear Algebra")
```

Use `MathTex` for mathematical expressions:

```python
MathTex(r"\vec{v} = \begin{bmatrix} x \\ y \end{bmatrix}")
```

**Example**

```python
from manim import *

class TextExample(Scene):

    def construct(self):

        title = Text("Pythagorean Theorem")
        equation = MathTex(r"a^2 + b^2 = c^2")

        title.to_edge(UP)
        equation.next_to(title, DOWN)

        self.play(Write(title))
        self.play(Write(equation))

        self.wait(2)
```

---

## **`Transformations`**

Manim can transform one object into another.

`Transform`

```python
self.play(
    Transform(square, circle)
)
```

This transforms the square into a circle.

`ReplacementTransform`

```python
self.play(
    ReplacementTransform(square, circle)
)
```

Transformations are particularly useful for explaining mathematical steps.

---

## **`Example: Equation Transformation`**

```python
from manim import *

class Algebra(Scene):

    def construct(self):

        equation1 = MathTex("x + 2 = 5")
        equation2 = MathTex("x = 3")

        self.play(Write(equation1))
        self.wait(1)

        self.play(
            Transform(equation1, equation2)
        )

        self.wait(2)
```

This can visually represent:

```text
x + 2 = 5
    ↓
  x = 3
```

---

## **Animating with `.animate`**

Manim provides the `.animate` syntax for animating transformations.

Example:

```python
from manim import *

class AnimateExample(Scene):

    def construct(self):

        square = Square()

        self.play(Create(square))

        self.play(
            square.animate.shift(RIGHT)
        )

        self.wait(2)
```

The square smoothly moves to the right.

Another example:

```python
self.play(
    square.animate.scale(2)
)
```

This enlarges the square.

---

## **`Colors`**

Mobjects can be given colors.

```python
circle = Circle(color=BLUE)
```

Or:

```python
circle.set_color(RED)
```

Example:

```python
from manim import *

class ColorExample(Scene):

    def construct(self):

        circle = Circle(color=BLUE)

        self.play(Create(circle))

        self.play(
            circle.animate.set_color(RED)
        )

        self.wait(2)
```

---

## **`Groups`**

Multiple Mobjects can be grouped using `VGroup`.

```python
from manim import *

class GroupExample(Scene):

    def construct(self):

        circle = Circle()
        square = Square()
        triangle = Triangle()

        group = VGroup(
            circle,
            square,
            triangle
        )

        group.arrange(RIGHT)

        self.play(Create(group))

        self.wait(2)
```

This is useful when several objects should be treated as a single group.

---

## **`Coordinate Systems`**

Manim is extremely useful for visualizing graphs and coordinate systems.

Example:

```python
from manim import *

class CoordinateExample(Scene):

    def construct(self):

        axes = Axes(
            x_range=[-5, 5],
            y_range=[-3, 3]
        )

        self.play(Create(axes))

        self.wait(2)
```

---

## **`Graphing Functions`**

We can use coordinate systems to visualize mathematical functions.

Example:

```python
from manim import *

class GraphExample(Scene):

    def construct(self):

        axes = Axes(
            x_range=[-5, 5],
            y_range=[-5, 5]
        )

        graph = axes.plot(
            lambda x: x**2,
            x_range=[-2, 2]
        )

        self.play(Create(axes))
        self.play(Create(graph))

        self.wait(2)
```

This creates the graph:

```text
y = x²
```

---

## **`Linear Algebra with Manim`**

Manim is excellent for visualizing linear algebra.

For example:

```text
Vectors
   ↓
Matrices
   ↓
Linear Transformations
   ↓
Eigenvectors
   ↓
Eigenvalues
   ↓
Vector Spaces
```

Example vector:

```python
from manim import *

class VectorExample(Scene):

    def construct(self):

        plane = NumberPlane()

        vector = Arrow(
            ORIGIN,
            [3, 2, 0],
            buff=0
        )

        label = MathTex(r"\vec{v}")

        label.next_to(vector, UP)

        self.play(Create(plane))
        self.play(Create(vector))
        self.play(Write(label))

        self.wait(2)
```

---

## **`Animating Linear Transformations`**

Manim can visually demonstrate how a transformation changes a coordinate plane.

Conceptually:

```text
Original Plane
      ↓
Transformation Matrix
      ↓
Transformed Plane
```

This is particularly useful for understanding:

* Scaling
* Rotation
* Reflection
* Shearing
* Matrix transformations

---

## **`3D Animations`**

Manim also supports 3D scenes.

A 3D scene can be created using:

```python
ThreeDScene
```

Example:

```python
from manim import *

class ThreeDExample(ThreeDScene):

    def construct(self):

        sphere = Sphere()

        self.set_camera_orientation(
            phi=60 * DEGREES,
            theta=45 * DEGREES
        )

        self.play(Create(sphere))

        self.wait(2)
```

Manim provides both Cairo and OpenGL renderer options.

---

## **Rendering Quality**

Manim provides different rendering-quality options.

Common CLI flags include:

```text
-pql
-pqm
-pqh
```

Generally:

```text
Low Quality
    ↓
Medium Quality
    ↓
High Quality
```

For example:

```bash
manim -pql scene.py MyScene
```

is useful during development because rendering is faster.

For a final render:

```bash
manim -pqh scene.py MyScene
```

---

## **`Useful Manim Commands`**

`Render a Scene`

```bash
manim scene.py MyScene
```

`Preview After Rendering`

```bash
manim -p scene.py MyScene
```

`Low Quality`

```bash
manim -pql scene.py MyScene
```

`Medium Quality`

```bash
manim -pqm scene.py MyScene
```

`High Quality`

```bash
manim -pqh scene.py MyScene
```

`List Available Scenes`

```bash
manim scene.py
```

---

## **`Output Structure`**

After rendering, Manim generates media files.

A typical project may contain:

```text
project/
│
├── scene.py
│
└── media/
    ├── images/
    └── videos/
```

The exact output location depends on Manim's configuration.

---

## **`Typical Manim Workflow`**

The basic workflow is:

```text
1. Create Python File
        ↓
2. Import Manim
        ↓
3. Create Scene
        ↓
4. Create Mobjects
        ↓
5. Position Mobjects
        ↓
6. Animate Mobjects
        ↓
7. Render Scene
        ↓
8. Get Video
```

---

## **`Manim Project for Math Videos`**

For a mathematical education project, you can organize your files like this:

```text
MathVideos/
│
├── main.py
│
├── scenes/
│   │
│   ├── algebra/
│   │   ├── equations.py
│   │   └── quadratic.py
│   │
│   ├── calculus/
│   │   ├── derivatives.py
│   │   └── integration.py
│   │
│   ├── linear_algebra/
│   │   ├── vectors.py
│   │   ├── matrices.py
│   │   └── eigenvalues.py
│   │
│   └── geometry/
│       ├── triangles.py
│       └── circles.py
│
├── assets/
│
├── media/
│
└── README.md
```

---

## **`Manim for AI-Generated Math Videos`**

Manim can also be used as the **visual generation engine** for an AI-powered math-video system.

A possible architecture is:

```text
                 User
                  │
                  ↓
        "Explain Eigenvalues"
                  │
                  ↓
             AI / LLM
                  │
                  ↓
        Generate Explanation
                  │
                  ↓
        Generate Manim Code
                  │
                  ↓
        Validate / Fix Code
                  │
                  ↓
              Manim
                  │
                  ↓
          Render Animation
                  │
                  ↓
              MP4 Video
```

This approach is particularly powerful because the AI does not need to manually draw the animation.

Instead, it can generate Python code such as:

```python
class EigenvalueExplanation(Scene):

    def construct(self):

        equation = MathTex(
            r"A\vec{v} = \lambda\vec{v}"
        )

        self.play(Write(equation))
        self.wait(2)
```

Manim then turns the code into an animation.

---

## **`Manim + AI Pipeline`**

A more complete system could look like:

```text
User Input
    │
    │
    ▼
┌───────────────┐
│  LLM / AI     │
└───────┬───────┘
        │
        ▼
Explanation
        │
        ▼
Manim Code Generation
        │
        ▼
Code Validation
        │
        ▼
Manim Renderer
        │
        ▼
Video Generation
        │
        ▼
Optional Voice Generation
        │
        ▼
Final Educational Video
```

This allows you to build an AI system that can transform a request such as:

```text
"Explain matrix multiplication visually."
```

into an educational animation.

---

## **`Example: Simple Math Video`**

```python
from manim import *

class MatrixMultiplication(Scene):

    def construct(self):

        title = Text("Matrix Multiplication")

        equation = MathTex(
            r"A \times B = C"
        )

        title.to_edge(UP)

        self.play(Write(title))
        self.play(Write(equation))

        self.wait(2)
```

A more advanced version could animate:

```text
Matrix A
   ×
Matrix B
   ↓
Multiply corresponding elements
   ↓
Add the products
   ↓
Matrix C
```

---

## **`Learning Path`**

If your goal is to create mathematical educational videos, learn Manim in this order:

```text
1. Python Basics
       ↓
2. Manim Installation
       ↓
3. Scene
       ↓
4. Mobjects
       ↓
5. Animations
       ↓
6. Positioning
       ↓
7. Text and MathTex
       ↓
8. Transformations
       ↓
9. Groups and VGroups
       ↓
10. Coordinate Systems
       ↓
11. Graphs
       ↓
12. Linear Algebra Visualizations
       ↓
13. Calculus Visualizations
       ↓
14. 3D Animations
       ↓
15. Advanced Animations
       ↓
16. AI + Manim
```

---

## **`Important Manim Classes`**

| Class         | Purpose                           |
| ------------- | --------------------------------- |
| `Scene`       | Creates a 2D animation scene      |
| `ThreeDScene` | Creates a 3D animation scene      |
| `Mobject`     | Base class for displayed objects  |
| `VGroup`      | Groups multiple Mobjects          |
| `Text`        | Displays normal text              |
| `MathTex`     | Displays mathematical expressions |
| `Circle`      | Creates a circle                  |
| `Square`      | Creates a square                  |
| `Triangle`    | Creates a triangle                |
| `Line`        | Creates a line                    |
| `Arrow`       | Creates an arrow                  |
| `Axes`        | Creates coordinate axes           |
| `NumberPlane` | Creates a coordinate plane        |

---

## **`Important Animations`**

| Animation                | Purpose                                 |
| ------------------------ | --------------------------------------- |
| `Create()`               | Creates/draws a Mobject                 |
| `Write()`                | Writes text or mathematical expressions |
| `FadeIn()`               | Fades an object into the scene          |
| `FadeOut()`              | Fades an object out                     |
| `Transform()`            | Transforms one Mobject into another     |
| `ReplacementTransform()` | Replaces one Mobject with another       |
| `Rotate()`               | Rotates a Mobject                       |
| `GrowArrow()`            | Animates an arrow growing               |
| `.animate`               | Animates method-based changes           |

---

## **`Best Practices`**

`1. Start With Low Quality`

During development:

```bash
manim -pql scene.py SceneName
```

This makes iteration faster.

`2. Keep Scenes Small`

Instead of creating one huge scene:

```text
HugeScene
```

create smaller scenes:

```text
Introduction
Concept
Example
Visualization
Conclusion
```

`3. Use Meaningful Names`

Prefer:

```python
matrix_a
matrix_b
result_matrix
```

instead of:

```python
x
y
z
```

`4. Separate Explanation From Animation`

For AI-generated videos, keep:

```text
Explanation
```

separate from:

```text
Manim Code
```

This makes the system easier to debug.

`5. Render Frequently`

Test small parts of an animation before creating the complete video.

---

## **`Common Mistakes`**

`Forgetting to Import Manim`

Incorrect:

```python
class MyScene(Scene):
```

Correct:

```python
from manim import *

class MyScene(Scene):
```

`Forgetting construct()`

A basic Scene should define its animation inside:

```python
def construct(self):
```

`Forgetting self.play()`

Creating an object does not automatically animate it.

```python
circle = Circle()
```

Use:

```python
self.play(Create(circle))
```

to animate it.

---

## **`Key Takeaways`**

* **Manim is a Python library for mathematical animations.**
* `Scene` represents the animation environment.
* `Mobject` represents objects displayed in the scene.
* `Animation` controls how Mobjects change over time.
* `MathTex` is used to display mathematical equations.
* `Axes` and `NumberPlane` are useful for mathematical graphs.
* Manim can create both 2D and 3D mathematical animations.
* Manim can be combined with an **LLM/AI system** to automatically generate educational math videos.

---

