# WebGL_ClassNotes

**Why :**

This is a repository of notes and resources for the subject taught by
the lecturer who prefers to deliver all the content verbally.

Challenges :

* Missing a class or a part of it could result in losing valuable information.
* Test scope is vague and unpredictable, based on what was mentioned but not done in class.
* Topics on webgl are not demonstrated or documented clearly, only
  explained verbally and sometimes referred to google or student examples.
* The only leniency is that the output on the screen is what matters,
  regardless of the implementation, unless some specific methods or
  practices are required (e.g. shader source code in a separate file).

---

## This is my solution.

##### A concise and clear documentation of the lectures we had so far.

---

My boiler plate code HelloTriangle [https://github.com/230500226/WebGL_HelloTriangle]()

---

#### Lecture 1 (31/01/2024)

---

##### [https://github.com/230500226/WebGL_HelloWorld]()

* 3 demo files - no error checking shown nor required but highly recommeded for debugging
  * Point
    * index.html doesnt change throught
      * add a canvas tag
        * dont use css for this it gets buggy just insert styles directly, then use css file for everything else (buttons)
      * add a script main.js
    * main.js
      * using webgl1 - basic code for a point
      * canvas is 2d - webgl is 3d
      * w is always 1 (x,y,z is divided by w)
    * main1.js
      * using webgl2 - basic code for a point
    * main2.js
      * just like main.js but
        * Error checks for webgl context
        * BackgroundColor yellow
        * Uses buffer instead of vertices in the shader code
  * Line
    * explained the verrtexAttribPointer
      * webgl.vertexAttribPointer(index, size, type, normalized, stride, offset);
      * webgl.vertexAttribPointer(positionLocation, 2, webgl.FLOAT, false, 0, 0);
    * explained the drawArrays draw call
      * webgl.drawArrays(webgl.LINE_STRIP, 0, 5);
      * webgl.drawArrays(webgl.LINES, 0, 5);
      * webgl.drawArrays(webgl.LINE_LOOP, 0, 5);
  * Triangle
    * explained the clearColor & clear functions
      * webgl.clearColor(1.0,1.0,0,1); //r=0 g=1 b=0 values red green blue 1 0 ; rgba
      * webgl.clear(webgl.COLOR_BUFFER_BIT);
* test (live class instructions demo)
  * const canvas can use
    * `document.querySelector`
      * searches for the first canvas element in the html
    * ```
      document.getElementById
      ```

      * searches for the canvas with specific ID
  * use backtick when creating the source code variable

---

#### Lecture 2 (07/02/2024)

* Be familliar with
  * the terms clipping space, world, view, camera
  * changing x,y values to translate a shape
    * use uniform, requestAnimationFrame
    * use a button styled with a separate css file
* Task :
  * Make the three shapes move around the canvas and bounce of the walls
  * Use a button to start and stop the movement
  * [https://github.com/230500226/WebGL_3ShapesMove]()

---

#### Lecture 3 (14/02/2024)

* Task :
  * Make a shape rotate using the formula

    1. The new x-coordinate (x') after rotating a point (x, y) by an angle θ counterclockwise is given by:
       $$
       x' = r \cos(\phi + \theta) = r \cos\phi \cdot \cos\theta - r \sin\phi \cdot \sin\theta = x \cos\theta - y\sin\theta
       $$
    2. The new y-coordinate (y') after the rotation is given by:
       $$
       y' = r \sin(\phi + \theta) = r \cos\phi  \cdot  \sin\theta + r \sin\phi \cdot \cos\theta = x \sin\theta + y \cos\theta
       $$

    These formulas describe the rotation of a point (x, y) by an angle θ counterclockwise. The variables r, φ, and θ represent the radius, the original angle, and the rotation angle, respectively. The prime symbols (') indicate the new coordinates after rotation.
  * [https://github.com/230500226/WebGL_3ShapesMove]()
  * Make 2 objects bounce off the walls and when colliding with the main object the other object should shake then disappear
  * 

---

#### Lecture 4 (21/02/2024)

* Task :
  * Make an object rotate in the x, y, z axis and use buttons to toggle the rotation
  * [https://github.com/230500226/WebGL_TriangleRotate]()

---

#### Lecture 5 (28/02/2024)

* Task :
  * create a cube
  * rotate the cube

---

#### Lecture 6 (6/03/2024)

* Task :
  * create a sphere


##### [https://github.com/230500226/WebGL_3Shapes/blob/main/3shapes.js]()

* Make three different shapes in the same canvas

##### familiar with vary use within vertexShaderSourceCode - contains value within vertex shader and fragment shader

    - value of vary are same as attribute

    - value for var1 link to var2 inside main function

    - create varrying in frag and vertex shader with same name

    - allow for calculation of clour gradient between colours (top green, bottomL blue, bottomR red)
             - use precision for colour acc.

### use separate shader source code in separate files

//2/28/2024
        create a triangle
        randomise color of triangle - use button

    create cube different colors - test
                pass each color through vertex shader
                use button to rotate
us gl.enable(gl.depthTest)

extra
        using a points
        create array for color and verticies
        specify array using the bing first
                use 2 buffers

use separate buffer for color and vertex
and know how to use one buffer for color and vertex

to make a circle
  use the rotate formula provided by whatsapp
  then use 360/4 to make a square then 360/36 or more for a circle
  look at day 2

  no longer use multiplication within vertexshader
  use 4x4 mat4 id matrix - starting point for all objects in the world
    then multiply that id matrix to the translation matrix
      the resultant matix will look like the transformation (get values of the 16 points)
        this is the code that will appear in the function translate
        wont use 2 dimensional matrix - nothing called 2 dimensional array
        create a matrix thats 2d look for memory in c and look for depth

    id matrix will be 1 dimensional array aswall as translation matrix
        use 16 element array - array that starts from r0 to r15
          asking to conceptualise the values of r0 to r15
          a{mat) x b{mat}
            use r[0] to r[15]

    know what a translation matrix is
    a matrix that will give desired values as result

    used to add vec4 foreach axis to ratoat
              withing matrix use multiplication
                add all entries of the matrix

    start with resultant matrix then find out he translatino matrix
            3 matrix for rotation x y z
            1 matrix for translation
            all together 4 transformation matrix
            and a scaling matrix (multiply all values by the scaling factor)
              start point is a vector result is a vector, use a matrix multiplication to get the result

    if a point x , increase the value of w the x increases
              w can be used to describe a direction of a vector
              not used for this course

    change the colour of points of the triagnle use separate bufferes for color and verticies and change the colors randomly
        06/03
        instructions
          make a sphere, pentagon, diamond
           - out of context use matrix for rot and trans use id matrix
          make sphere
