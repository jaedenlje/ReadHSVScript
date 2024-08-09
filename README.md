
# Read HSV Value Script (OpenCV)
## Description
This project is designed to process and analyze images within a specified folder by converting each image to the HSV (Hue, Saturation, Value) colour space, displaying the mean HSV values for each image, and then showing the image using OpenCV's imshow function.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Installation
Install [PyCharm Community Edition](https://www.jetbrains.com/pycharm/download/?section=windows)

## Usage
To use the script, you need to provide the path to the test image folder containing the traffic light images.

    1. Update the test_folder variable in the script with the appropriate paths.
    2. Run the script:

### Example
    
    import cv2
    import numpy as np
    import os

    # Load test image folder
    test_folder = "/path/to/your/test/folder"

    # Loop through all images in the test folder
    for filename in os.listdir(test_folder):
        # Load image
        image_path = os.path.join(test_folder, filename)
        image = cv2.imread(image_path)

        # Convert image to HSV
        hsv_image = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)

        # Display HSV values
        print(f"HSV values for {filename}:")
        print(f"H: {hsv_image[:, :, 0].mean()}")
        print(f"S: {hsv_image[:, :, 1].mean()}")
        print(f"V: {hsv_image[:, :, 2].mean()}")

        # Display image
        cv2.imshow("Image", image)
        cv2.waitKey(0)
        cv2.destroyAllWindows()

## License
This project is licensed under the [MIT License](https://www.mit.edu/~amini/LICENSE.md).



