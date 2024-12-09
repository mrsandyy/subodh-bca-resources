# UNIT-I: Introduction to Computer Graphics

## 1. Definition of Computer Graphics

Computer graphics is the field of study and practice that involves the creation, manipulation, and representation of visual content using computers. It encompasses a wide range of techniques and technologies for generating and processing digital images.

**Key aspects:**

- Computer graphics involves both 2D and 3D visual content
- It includes the creation, storage, manipulation, and display of images
- The field combines elements of computer science, mathematics, and visual arts
- It deals with both vector and raster graphics
- Computer graphics is fundamental to modern user interfaces and visual computing

## 2. Application Areas of Computer Graphics

Computer graphics has permeated numerous fields, revolutionizing how we visualize and interact with information.

**Detailed breakdown:**

1. **Entertainment**:
   
   - Video games: 3D modeling, texturing, animation, and real-time rendering
   - Movies: Special effects, CGI (Computer-Generated Imagery), animated films
   - Virtual Reality (VR) and Augmented Reality (AR): Immersive experiences, 3D environments

2. **Education**:
   
   - Interactive learning tools: Visual simulations, 3D models of complex systems
   - Training simulators: Flight simulators, medical procedure training
   - Educational software: Engaging visuals for better understanding of concepts

3. **Science and Engineering**:
   
   - Data visualization: Turning complex datasets into understandable visual representations
   - CAD (Computer-Aided Design): Designing products, buildings, and mechanical parts
   - Simulation: Modeling physical phenomena, testing designs virtually

4. **Medicine**:
   
   - Medical imaging: Processing and visualizing MRI, CT scans, and X-rays
   - Surgical planning: 3D modeling of organs for pre-operative planning
   - Prosthetics design: Custom-fit prosthetics using 3D scanning and modeling

5. **Business**:
   
   - Advertising: Creating eye-catching graphics and animations
   - Data presentation: Infographics, charts, and interactive dashboards
   - Product design: Conceptualizing and prototyping products virtually

6. **Art and Design**:
   
   - Digital art: Creating artwork directly on computers
   - Graphic design: Logos, layouts, and visual branding
   - Web design: Creating visually appealing and functional websites

## 3. Graphical User Interface (GUI)

A Graphical User Interface is a visual way of interacting with electronic devices through graphical elements rather than text-based interfaces.

**Key points:**

- **Definition**: A system of interactive visual components for computer software
- **WIMP paradigm**: Windows, Icons, Menus, Pointer - the core elements of most GUIs
- **Event-driven programming**: The GUI responds to user actions (events) like clicks or key presses
- **Widgets**: Reusable GUI components such as buttons, text boxes, sliders, and dropdown menus
- **Advantages**: More intuitive for users, easier to learn than command-line interfaces
- **Challenges**: Requires more system resources, can be slower than text-based interfaces for expert users

**Historical context**: 

- Developed at Xerox PARC in the 1970s
- Popularized by Apple with the Macintosh in 1984
- Became widespread with Microsoft Windows in the 1990s

## 4. Display Technologies

### 4.1 Cathode Ray Tubes (CRT)

CRT is a vacuum tube containing electron guns and a fluorescent screen used to view images.

**Detailed description:**

- Electron guns emit beams of electrons
- Beams are focused and accelerated towards the screen
- Deflection coils direct the beam to scan across the screen
- Phosphor coating on the screen emits light when struck by electrons
- Images are formed by rapidly scanning the electron beam across the screen

**Types of CRT displays:**

#### 4.1.1 Random Scan Displays (Vector Displays)

- Draw images using lines by directly controlling the electron beam
- High precision for line drawings
- Limited to wireframe images
- Used in early CAD systems and oscilloscopes

#### 4.1.2 Raster Scan Displays

- Scan the electron beam in a fixed pattern (left to right, top to bottom)
- Create images using a matrix of pixels
- Can display complex images and colors
- Basis for modern TV and computer monitors

### 4.2 Color CRT Monitors

**Detailed description:**

- Use three electron guns, one each for Red, Green, and Blue
- Employ a shadow mask or aperture grille to direct electron beams
- Each pixel on the screen consists of red, green, and blue phosphor dots
- Combine RGB phosphors in varying intensities to create full-color images
- Offer high contrast ratios and good color reproduction

### 4.3 Flat Panel Displays

Modern display technologies that offer advantages over CRTs in terms of size, weight, and power consumption.

#### 4.3.1 Plasma Panels

**Key points:**

- Contain cells filled with ionized gas (plasma)
- Each cell acts as a tiny fluorescent lamp
- Produces light through electrical stimulation of the gas
- Offers high contrast ratios and wide viewing angles
- Challenges include high power consumption and potential for screen burn-in

#### 4.3.2 Liquid Crystal Displays (LCD)

**Detailed description:**

- Use liquid crystals to control light passage
- Backlight illuminates the display (usually LED in modern displays)
- Pixels consist of liquid crystal layers between polarizing filters
- Electric current alters crystal alignment to allow/block light
- Types include TN (fast, cheap), IPS (better color and viewing angles), and VA (high contrast)
- Advantages: Low power consumption, no geometric distortion
- Disadvantages: Limited viewing angles (improved in modern panels), potential for dead pixels

#### 4.3.3 Electroluminescent Displays

**Key aspects:**

- Use phosphor materials that emit light when electric current is applied
- Very thin and energy-efficient
- High contrast and wide viewing angles
- Often used in small devices or as backlights
- Examples include OLED (Organic Light Emitting Diode) displays
- OLED advantages: Perfect blacks, vibrant colors, potential for flexible displays

## 5. Graphics Software

### 5.1 Graphical Kernel System (GKS)

**Detailed description:**

- First ISO standard for graphics programming
- Provides a set of drawing primitives for 2D graphics
- Aims for device-independent graphics output
- Key features:
  - Output primitives: lines, polygons, text
  - Input handling for various devices
  - Coordinate systems and transformations
  - Segmentation for grouping graphical elements
- Limitations: Primarily focused on 2D graphics, lacks advanced 3D capabilities

### 5.2 Programmer's Hierarchical Interactive Graphics System (PHIGS)

**Key points:**

- Extension of GKS to support 3D graphics
- Designed for interactive applications and complex scenes
- Supports hierarchical structure of graphical data
- Key concepts:
  - Structures and elements for organizing graphical data
  - Viewing and modeling transformations for 3D manipulation
  - Input handling and events for user interaction
  - Support for animation and dynamic scenes
- Advantages over GKS: Better suited for CAD/CAM applications, supports complex 3D scenes

## 6. Color Models

Mathematical systems for representing colors in digital systems.

### 6.1 RGB (Red, Green, Blue)

**Detailed description:**

- Additive color model based on light emission
- Primary colors: Red, Green, Blue
- Colors created by combining different intensities of these primaries
- Each color typically represented by 8 bits (0-255) per channel
- Used in displays, digital cameras, and image processing
- Represents a wide color gamut suitable for electronic displays
- Example: RGB(255, 0, 0) represents pure red

### 6.2 CMYK (Cyan, Magenta, Yellow, Key/Black)

**Key aspects:**

- Subtractive color model based on light absorption
- Used primarily in printing processes
- Primary colors: Cyan, Magenta, Yellow, with Black added for deeper shadows and text
- Colors created by absorbing light with different combinations of inks
- Each color represented as a percentage (0-100%) of ink coverage
- More suitable for reproducing colors on physical media
- Example: CMYK(0%, 100%, 100%, 0%) represents pure red in print

### 6.3 HSV (Hue, Saturation, Value)

**Detailed description:**

- Represents colors in a way that's closer to human perception
- Components:
  - Hue: Color type (0-360 degrees on the color wheel)
  - Saturation: Color intensity or purity (0-100%)
  - Value: Brightness (0-100%)
- Intuitive for color selection and manipulation in graphics software
- Easier for humans to reason about than RGB or CMYK
- Example: HSV(0°, 100%, 100%) represents pure red

## 7. Color Lookup Table

**Detailed description:**

A Color Lookup Table (CLUT) is a mechanism used in computer graphics to reduce memory requirements and speed up display processes.

Key characteristics:

- Stores a limited palette of colors (typically 256 in 8-bit color systems)
- Each entry contains RGB values for a specific color
- Pixels in the image store an index to the table instead of full color information

Functionality:

- When displaying an image, the system looks up the color values for each pixel
- Changing colors in the table affects all pixels referencing those entries

Benefits:

- Reduces memory usage for images
- Allows quick color changes by modifying the table
- Useful for creating visual effects (e.g., color cycling in old video games)
- Can optimize color usage for specific images or applications

Limitations:

- Restricts the number of colors that can be displayed simultaneously
- Not suitable for photorealistic images requiring millions of colors

Historical significance:

- Crucial in early computer graphics with limited memory and processing power
- Still used in some specialized applications and in color quantization algorithms

Example application:
In a 256-color system, instead of storing 3 bytes (24 bits) of RGB data per pixel, only 1 byte (8 bits) is needed to reference the color in the CLUT, potentially reducing memory usage by 66%.
