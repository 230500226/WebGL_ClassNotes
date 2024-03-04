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
    * `document.querySelector(`
      * searches for the first canvas element in the html
    * document.getElementById
      * searches for the canvas with specific ID
  * use backtick when creating the source code variable

---

#### Lecture 2 (07/02/2024)

---

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
