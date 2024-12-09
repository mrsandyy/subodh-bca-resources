# UNIT-III: Two-Dimensional Clipping and Visible Surface Detection Methods

This unit focuses on two-dimensional clipping techniques and visible surface detection algorithms used in computer graphics. The main objective of these algorithms is to determine which parts of objects are visible in the view frustum (the visible area in a scene).

---

### **1. Viewing Pipeline, Window, and Viewport**

- **Viewing Pipeline**:  
  The viewing pipeline is the process of transforming the 3D world coordinates to the 2D screen coordinates for rendering. It involves several stages, including the definition of the viewport, window, projection, and clipping. The pipeline transforms objects in the world space to camera space, then to projection space, and finally to device coordinates.

- **Window and Viewport**:
  
  - **Window**: Refers to the rectangular area in the world coordinate system that defines the portion of the scene to be visible. The window acts as the "camera" that captures a part of the world.
  
  - **Viewport**: Refers to the rectangular area on the screen (device coordinate system) where the window will be mapped. The viewport determines where and how the window’s contents are displayed.
  
  - **Transformation**:  
    A window-to-viewport transformation maps the contents of the window into the viewport on the screen. This transformation ensures that the visible area from the window is correctly placed on the display.
    
    **Formula**:
    
    - If are the coordinates in the window and are the coordinates in the viewport, then the mapping can be done by:
    
    ```plaintext
    V_x = (W_x - W_{min}) * \frac{V_{max} - V_{min}}{W_{max} - W_{min}} + V_{min}
    V_y = (W_y - W_{min}) * \frac{V_{max} - V_{min}}{W_{max} - W_{min}} + V_{min}
    ```

---

### **2. Clipping Algorithms**

Clipping is the process of removing the portions of an object that lie outside a specified region or window.

#### **2.1 Sutherland-Cohen Line Clipping Algorithm**

- **Description**:  
  This algorithm is used to clip a line segment against a rectangular window. The basic idea is to assign a code (outcode) to each endpoint of the line, based on which region of the window the point lies in.

- **Algorithm Steps**:
  
  1. Assign a 4-bit outcode for each endpoint of the line.
  2. Perform logical tests to check whether the line is inside, outside, or partially inside the clipping window.
  3. If the line is partially inside, calculate the intersection of the line with the window boundaries.
  4. Repeat until the line is completely clipped or fully inside the window.

- **Outcode**:  
  The 4-bit outcode is used to represent the position of a point relative to the clipping window:
  
  - Top: 1000
  - Bottom: 0100
  - Right: 0010
  - Left: 0001
  - Inside: 0000

#### **2.2 Cyrus-Beck Algorithm**

- **Description**:  
  The Cyrus-Beck algorithm is a more general line clipping algorithm that works for convex polygonal clipping windows. It uses parametric equations to determine the intersection points of the line with the window boundaries.

- **Algorithm Steps**:
  
  1. Represent the line segment as a parametric equation.
  2. For each edge of the clipping window, compute the parameter where the line intersects the edge.
  3. Use these parameters to determine the portion of the line that lies within the window.

- **Advantages**:
  
  - Handles arbitrary convex polygons as clipping windows.
  - More efficient than the Sutherland-Cohen algorithm for non-rectangular clipping windows.

---

### **3. Visible Surface Detection Algorithms**

Visible surface detection is the process of determining which surfaces of an object are visible from a specific viewpoint. This is crucial in 3D graphics to optimize rendering by displaying only the visible parts of objects.

#### **3.1 Classification of Visible Surface Detection Algorithms**

Visible surface detection algorithms can be classified into the following categories:

1. **Image-space algorithms**:  
   These algorithms work by checking which parts of the image are visible. They typically use the frame buffer to check visibility and eliminate hidden surfaces.
   
   - **Example**: Z-buffer algorithm.

2. **Object-space algorithms**:  
   These algorithms check visibility by comparing the geometry of the objects in space. They are often computationally intensive but more accurate.
   
   - **Examples**: Backface removal, depth sorting, area subdivision.

3. **Hybrid methods**:  
   These combine elements of both image-space and object-space algorithms to improve efficiency and accuracy.

#### **3.2 Backface Algorithm**

- **Description**:  
  The backface culling algorithm removes the surfaces of an object that are facing away from the viewer, which are not visible. This is done by calculating the normal of each face and comparing it to the viewer's direction. If the face is oriented away from the viewer, it is discarded.

- **Mathematical Formula**:  
  For a polygon with normal vector and a view vector , the backface is determined by:
  
  ```plaintext
  N . V < 0
  ```
  
  - If the dot product of the normal vector and the view vector is less than zero, the face is a backface and is culled.

- **Advantages**:
  
  - Simple and fast.
  - Effective for convex objects where most of the back faces can be removed.

---

#### **3.3 Depth Sorting Method**

- **Description**:  
  The depth sorting method involves sorting all the polygons in a scene based on their depth from the viewer and then rendering them in back-to-front order. This method is often used with transparency and can handle overlapping objects.

- **Algorithm Steps**:
  
  1. Sort all polygons based on the z-coordinate or depth value.
  2. Render the polygons in reverse order (from the farthest to the nearest).
  3. For overlapping polygons, the nearest one is drawn on top.

- **Advantages**:
  
  - Simple to implement.
  - Works well for scenes with transparent objects.

---

#### **3.4 Area Subdivision Method**

- **Description**:  
  The area subdivision method involves dividing the entire scene into smaller regions or areas. These areas are then processed individually to determine which surfaces are visible. The division continues until the regions are small enough for efficient visibility testing.

- **Algorithm Steps**:
  
  1. Divide the area into smaller regions (subdivisions).
  2. For each region, check the visibility of the surfaces.
  3. Recur the subdivision process until the region size is small enough for direct comparison.

- **Advantages**:
  
  - Efficient for complex scenes with many surfaces.
  - Helps manage large amounts of data by focusing only on smaller regions.

---
