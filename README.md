# Seam Carving Project

## Overview
This project implements **seam carving**, an image resizing technique that removes or inserts seams (connected pixels) to reduce or expand the size of an image while preserving its key content. The technique is useful for **content-aware image resizing**, commonly applied in image processing and computer vision tasks.

## Features
- Reads and processes an input image.
- Computes energy maps using Sobel filters.
- Identifies and removes low-energy seams.
- Supports visualization of intermediate steps.

## Installation
### Prerequisites
Ensure you have the following dependencies installed:
```bash
pip install opencv-python numpy matplotlib
```

## Usage
### 1. Load an Image
Modify the script to specify your image path:
```python
image_path = 'path/to/your/image.jpg'
image = cv2.imread(image_path)
```

### 2. Compute Energy Map
```python
Gx = cv2.Sobel(img_grey, cv2.CV_64F, 1, 0, ksize=3)
Gy = cv2.Sobel(img_grey, cv2.CV_64F, 0, 1, ksize=3)
energy = np.sqrt(Gx**2 + Gy**2)
```

### 3. Visualize Energy Map
```python
plt.imshow(energy, cmap='gray')
plt.title("Energy Map")
plt.show()
```

### 4. Perform Seam Removal (if implemented)
Modify and run seam removal logic in the script.

## Example
Below is an example of an energy map visualization:
```python
fig, axes = plt.subplots(3, 1, figsize=(6, 12))
axes[0].imshow(Gx, cmap='gray')
axes[0].set_title("Edgeness in X")
axes[1].imshow(Gy, cmap='gray')
axes[1].set_title("Edgeness in Y")
axes[2].imshow(energy, cmap='gray')
axes[2].set_title("Energy Map")
plt.show()
```

## Contributing
Feel free to fork this repository, submit issues, or contribute by adding new features!

## License
This project is licensed under the MIT License.

