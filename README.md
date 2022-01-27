# A computer vision system for automated Rubik's cube solver

The goal of the project was to develop an algorithm that, given the face of a Rubik’s cube, can classify the colour of each cell and propose the next move.

It has been tested with prepared images available with this project and webcam input.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install requirements.txt

```bash
pip install requirements.txt
```

## Usage

Launch Jupyter Notebook and run ```RubiksCubeSolver.ipynb```.

Test images are placed in ```./images/```.
Default image folder is  ```./images/light/*```.

For using your own images change path in code accordingly. Images of cube faces should be ```*.jpg``` format with names from ```{"U","L","F","R","B","D"}```.

## Description
The problem has been solved using the [OpenCV](https://docs.opencv.org/4.2.0/) Python library and a [solver](https://github.com/pglass/cube).
### Solution steps (with adjustable parameters)
1. Square image - resized to 600x600 pixels.
2. Gaussian blur - 7x7 kernel.
3. Canny edge detection - (20,40) thresholds.
4. Edge dilation - 3x3 kernel, 4 iterations.
5. Contour filtering - 2,5-5% of image for each contour.
6. Colour matching - Saturation threshold for white, Hue ranges for colours
7. Building a model and solving.

## Contributing
The solution isn't robust to varying lighting. The color matching algorithm can be improved with a more detailed analysis as in ```ColorAnalysis.ipynb```.

At the end of the primary notebook there's also a suggestion for developing the system with webcam input.

## Author
[Kinga Kwoka](https://github.com/kzkwoka)

## License
[MIT](https://choosealicense.com/licenses/mit/)