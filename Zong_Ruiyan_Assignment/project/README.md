# Experiment Instructions

## Overview
This experiment tests a participant's ability to synchronize their key presses with a bouncing basketball.

## How to Run the Experiment
1. Make sure you have a web browser (Chrome, Firefox, or Edge recommended).
2. Place all files in the same folder:
   - `index.html` (your experiment file)
   - `basketball.png` (the ball image)
   - `jspsych` folder (containing jsPsych library files)
3. Open `index.html` in your browser.

## How to Participate
1. Read the instructions and consent form.
2. Press any key to start.
3. Watch the bouncing ball and press `SPACE` when you think it hits the ground.
4. Complete six trials. A "Next Trial" screen will appear between trials.
5. After all trials, a debrief screen will appear.
6. Your data will be saved as `mydata.csv`, click `proceed` to download.

## Customization
- Change the ball's behavior by modifying the `basketballTask` settings.
- Adjust the number of trials in `test_procedure` (currently set to 6).
- Modify the instructions and consent form text inside `instructions` and `consent` blocks.

## Troubleshooting
- If the experiment does not start, check the browser console (`F12` -> Console tab) for errors.
- Ensure all necessary files (images and `jspsych` library) are in the correct locations.
