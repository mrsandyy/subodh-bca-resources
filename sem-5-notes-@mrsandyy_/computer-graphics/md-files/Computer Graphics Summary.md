# Briefing Document: Computer Graphics

This briefing document reviews key themes and concepts from provided sources regarding computer graphics and digital image processing. It covers fundamental principles, algorithms, and applications.

## I. Introduction to Computer Graphics

- **Definition:** Computer graphics encompasses the creation, manipulation, and representation of visual content using computers, including both 2D and 3D images.
  - "Computer graphics is the field of study and practice that involves the creation, manipulation, and representation of visual content using computers." - CG Unit 1
- **Applications:** Computer graphics finds applications in diverse fields like entertainment, education, engineering, medicine, and business. Examples include:
  - Creating realistic visual effects in films and video games.
  - Developing educational simulations and visualizations.
  - Designing and modeling products in industries like automotive and aerospace.
- **Hardware:** Key hardware components include:
  - **CRT:** Cathode Ray Tube displays, where an electron beam excites phosphor dots to emit light. Color CRTs use a shadow mask grid to direct beams to specific color dots (red, green, blue).
  - **Frame Buffer:** Also known as raster or bitmap, stores pixel information for display.
  - **Raster Scan:** Method for refreshing displays, involving horizontal and vertical retracing of the electron beam. Types include interlaced and non-interlaced scanning.
- **Graphics Software:**
  - **Graphical Kernel System (GKS):** First ISO standard for 2D graphics programming, focused on device-independent output.
  - **Programmer's Hierarchical Interactive Graphics System (PHIGS):** Extended GKS for 3D graphics, enabling interactive applications and complex scene management.
  - *"Advantages over GKS: Better suited for CAD/CAM applications, supports complex 3D scenes"*
- **Graphical User Interface (GUI):**
  - GUIs provide intuitive visual interaction with electronic devices, contrasting with text-based interfaces.
  - They employ elements like windows, icons, menus, and pointers (WIMP paradigm) in an event-driven programming model.
  - GUIs revolutionized user experience but can demand higher system resources compared to text-based interfaces.
  - *"Developed at Xerox PARC in the 1970s, Popularized by Apple with the Macintosh in 1984, Became widespread with Microsoft Windows in the 1990s"*
- **Color Models:** Represent colors mathematically for digital displays.
  - **RGB:** Additive model using red, green, and blue as primary colors. "All other colours are produced by the proportional ratio of these three colours only." widely used in displays and digital imaging.
  - **CMYK:** Subtractive model using cyan, magenta, yellow, and black, primarily used for printing.
  - **HSV (Hue, Saturation, Value):** Represents color aligned with human perception, simplifying color selection in graphics software.
- **Color Lookup Table (CLUT):** A table that maps color indices to actual color values, used for reducing memory usage.
  - A mechanism for memory optimization by storing a limited color palette, referencing them through indices.
  - Beneficial for early graphics systems with limited resources, while potentially restricting the number of displayed colors.

---

## II. Raster Graphics Algorithms and Transformations

- **Raster Graphics:** Represent images as a grid of pixels, where each pixel holds color information. Algorithms are used to convert geometric shapes into pixel representation.

- **Line Drawing Algorithms:** Generate pixel approximations of lines.
  
  - **Digital Differential Analyzer (DDA):** Incremental algorithm, simple but computationally expensive due to floating-point arithmetic.
  - **Bresenham's Algorithm:** More efficient than DDA, uses integer calculations. "Bresenham’s algorithm improves upon DDA by using integer-only calculations, making it faster and more efficient for raster displays." 

- **Circle Drawing:** Generate pixel approximation of circle.
  
  - **Midpoint Circle Algorithm:** Leverages circle symmetry to efficiently plot points in eight octants using integer arithmetic.
  
  - **Midpoint Ellipse Algorithm:** Extends the midpoint circle algorithm for drawing ellipses.

- **Polygon Filling:** Color enclosed areas within shapes.
  
  - **Scan Line Algorithm:** Fills polygons by intersecting scan lines with edges and filling between intersection points.
  
  - **Boundary Fill Algorithm:** Starts from a seed point and recursively fills neighboring pixels with the same color until a boundary is reached.
  
  - **Flood Fill Algorithm:** Similar to boundary fill, but does not rely on boundary color differences.
  
  - **Inside-Outside Test:** Determines whether a point is inside or outside a polygon, often used in filling algorithms.

- **Transformations:** Mathematical operations modifying object position, size, and orientation.

- **2D Transformations:** Mathematical operations to manipulate object position, size, and orientation in a 2D plane.
  
  - **Translation:** Moving an object along x and y axes.
  - **Rotation:** Rotating an object around a point.
  - **Scaling:** Changing the size of an object.
  - **Reflection:** Creating a mirror image of an object.
  - **Shearing:** Slanting an object horizontally or vertically.

- **Homogeneous Coordinates:** A representation adding a third coordinate for matrix multiplication-based transformations.

- **3D Transformations:** Extend 2D concepts to three dimensions.
  
  - **Translation, Rotation, Scaling, Reflection, and Shearing:** Analogous to 2D counterparts but in 3D space.
  - **Homogeneous Coordinates in 3D:** Simplify matrix representation for various transformations.

- **Composite Transformations:** Combine multiple transformations into a single operation for efficiency and simplicity.

---

## III. Two-Dimensional Clipping and Visible Surface Detection

- **Viewing Pipeline:** The process of transforming 3D world coordinates to a 2D screen representation. Involves steps like model transformation, viewing transformation, projection, and clipping.
  
  - **Window and Viewport:Window:** The area selected from the world coordinate system for display.
  - **Viewport:** The area on the display device (screen) where the window is mapped.

- **Clipping:** Removing portions of objects outside the defined window or viewing area.
  
  - **Sutherland-Cohen Algorithm:** Efficiently clips lines against a rectangular window using region codes for endpoints.
  - **Cyrus-Beck Algorithm:** A more general algorithm that can handle clipping against convex polygons.

- **Visible Surface Detection (VSD):** Determining which surfaces are visible from a given viewpoint, eliminating hidden surfaces.
  
  - **Classification:**
    
    - - **Image-Space Algorithms:** Operate on the image plane (e.g., Z-buffer algorithm).
      - **Object-Space Algorithms:** Analyze object geometry (e.g., backface removal, depth sorting).
      - **Hybrid Methods:** Combine both approaches.
  
  - **Depth Buffer (Z-Buffer) Method:** Compares surface depths at each pixel, storing the closest surface's intensity.
  
  - **Back Face Culling:** Eliminates surfaces facing away from the viewer.
  
  - **Scan Line Method:** Processes scan lines, comparing depths of intersecting surfaces to determine visibility.
  
  - **Depth Sorting (Painter's Algorithm):** Sorts polygons based on depth, rendering from back to front.
  
  - **Area Subdivision Method:** Divides the scene into regions for efficient visibility testing.

---

## IV. Digital Image Processing (DIP)

- **Definition:** The manipulation of digital images using computer algorithms to enhance quality, extract information, or prepare for analysis.

- **Applications:**
  
  - Medical imaging, remote sensing, computer vision, multimedia, industrial inspection, document processing.

- **File Formats:**
  
  - **Raster:** JPEG, PNG, GIF, TIFF.
  - **Vector:** SVG, EPS.
  - **Raw:** Unprocessed sensor data from cameras.

- **Basic DIP Techniques:**
  
  - **Antialiasing:** Reduces jagged edges by averaging pixel values.
  - **Convolutions:** Apply filters (kernels) for blurring, sharpening, edge detection, etc.
  - *"A kernel for sharpening: [ 0, -1, 0 ], [ -1, 5, -1 ], [ 0, -1, 0 ]"*
  - **Thresholding:** Converts grayscale to binary images by setting pixel values based on a threshold.
  - **Image Enhancement:** Improves image quality for various tasks.
  - Contrast enhancement, histogram equalization, brightness adjustment, linear contrast stretching, gamma correction.

- **Image Representation:** Digital images are represented as a grid of pixels, each storing color information.

- **Types:**
  
  - **Raster Images:** Composed of pixels, suitable for photographs and realistic images.
  - **Vector Images:** Based on mathematical equations, suitable for logos and illustrations.

- **Aliasing:** Visual artifacts (jagged edges) due to limited pixel resolution.
  
  - **Anti-Aliasing Techniques:** Methods to smooth jagged edges, including super-sampling, pre-filtering, and pixel phasing.
    - **Supersampling**: This involves rendering the image at a higher resolution and then downscaling it to the target resolution.
    - **Multisample Antialiasing (MSAA)**: A method used in 3D graphics to smooth edges by averaging samples taken from multiple points on the edges of objects.

- **Convolution:** Using kernels (small matrices) to modify pixel values, performing operations like blurring, sharpening, and edge detection.

- **Thresholding:** Converting a grayscale image to a binary image by setting a threshold value for pixel intensities.

- **Image Echnacement:** The process of improving the quality of an image by modifying its characteristics

- **Types of Image Enchacement:**
  
  - **Contrast Enhancement**: Enhancing the 
    difference between the light and dark regions of the image to improve 
    its visual clarity. 
  
  - **Histogram Equalization**: Adjusting the image's histogram. 
  
  - **Brightness Adjustment**: Adjusting the overall lightness or darkness of an image.

- **Image Enchancement Techniques**:
  
  - **Linear Contrast Stretching**: Used to increase contrast by stretching the range of pixel intensities.
  - **Gamma Correction**: Adjusts the brightness of an image to compensate for nonlinearities in display devices.

- **Spatial Domain Processing:** Image enhancement techniques operating directly on pixel values.
  
  - **Point Operations:** Apply the same transformation to each pixel individually, such as contrast adjustment.
