# Parking Space Detection System

## Overview
This project is a computer vision-based parking space detection system that identifies free and occupied parking spots using OpenCV and cvzone. The system processes a video feed of a parking lot, detects parked cars, and displays the number of available spaces in real time.

## Features
- Detects free and occupied parking spaces.
- Displays parking occupancy count in real time.
- Allows users to manually select and save parking spaces.
- Uses OpenCV for image processing and car detection.
- Stores parking space positions using `pickle`.

## Prerequisites
Ensure you have the following dependencies installed:

```bash
pip install opencv-python cvzone numpy
```

## Files
1. **`main.py`** - Detects parked cars and displays available spaces.
2. **`parkingList.py`** - Allows users to manually mark parking spaces and save them.
3. **`CarParkPos`** - A binary file storing parking space coordinates.
4. **`carPark.mp4`** - Video footage of the parking lot.
5. **`carParkImg.png`** - Image of the parking lot for manual marking.

## Usage
### Step 1: Mark Parking Spaces
Run the following script to manually define parking spots:
```bash
python parkingList.py
```
- Left-click to add a parking space.
- Right-click to remove a parking space.
- The positions are saved in `CarParkPos`.

### Step 2: Run Parking Detection
After defining spaces, run the detection script:
```bash
python main.py
```
This will:
- Process the video feed.
- Detect parked cars.
- Display free and occupied parking spaces.

## How It Works
1. **Marking Parking Spaces:**
   - Uses mouse events to mark parking spots and saves them in `CarParkPos`.
2. **Processing the Video Feed:**
   - Converts frames to grayscale.
   - Applies Gaussian blur and adaptive thresholding.
   - Identifies occupied spaces using non-zero pixel counts.
3. **Displaying Results:**
   - Draws colored rectangles over parking spaces.
   - Shows the count of free spaces in real time.

## Example Output
- **Green Rectangle:** Free space
- **Red Rectangle:** Occupied space
- **Counter Display:** `Free: X/Y`

## Future Improvements
- Implement a deep learning model for more accurate detection.
- Add a web-based interface for remote monitoring.
- Integrate with IoT sensors for real-time updates.

## License
This project is open-source and free to use under the MIT License.

