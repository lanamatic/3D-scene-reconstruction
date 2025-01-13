# 3D-scene-reconstruction
- This project performs 3D scene reconstruction using stereo images captured by the left and right cameras of the same phone. The reconstruction leverages intrinsic and extrinsic camera parameters, point correspondences, and stereo geometry principles.

# Workflow:
### Input Data:
  - Two images are captured from the same phone (left and right cameras).
  - The camera calibration matrix is known and identical for both cameras since the same phone is used.

<div style="display: flex; justify-content: center; gap: 10px;">
    <img src="/left-camera.jpeg" alt="Left Camera Image" width="300">
    <img src="/right-camera.jpeg" alt="Right Camera Image" width="300">
</div>
      

### Compute Fundamental and Essential Matrices:
   - Using matched points between the left and right images, we calculate the Fundamental Matrix.
   - The Essential Matrix is derived from the Fundamental Matrix using the known calibration matrix.
  
<div style="display: flex; justify-content: center; gap: 10px;">
    <img src="/left-points.png" alt="Left Camera Image with points labeled" width="300">
    <img src="/right-points.png" alt="Right Camera Image with points labeled" width="300">
</div>
  
### Essential Matrix Decomposition:
   - The Essential Matrix is decomposed to obtain:
        - The rotation and translation components between the two cameras.
        - The position of the left camera in the World Coordinate System (WCS), where the right camera's coordinate system is defined as the WCS.

### Camera Matrices:
  - Using the decomposed rotation and translation, the Camera Matrices for both cameras are calculated.
  - These matrices are used for triangulation.

### Triangulation:
  - Points from the left and right images are triangulated to compute the 3D coordinates of the scene points in the WCS.

### 3D Scene Visualization:
   - The reconstructed 3D points are visualized using Plotly to render an interactive 3D scene.

![3d-scene](/3d-reconstructed.png)

# Application of projective geometry in computing
Year: 2024/2025 \
Teaching Assistant: Milan Pavlović \
Professor: Srđan Vukmirović
