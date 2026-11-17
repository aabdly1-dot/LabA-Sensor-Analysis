# Recording Guide — do this before running the notebook

## Phone app and sensors

Use a phone with accelerometer (and optionally gyroscope/GPS). The supplied lab recommends:
- **Android:** Physics Toolbox Sensor Suite (Vieyra Software)
- **iOS or Android:** SensorLog; Sensor Play is also mentioned

Choose the **accelerometer** sensor with x/y/z axes. Aim for **50 Hz** (50 readings per second), or the nearest setting supported by the app. Note the actual configured rate. The phone alone is enough; a smartwatch is not necessary.

## Simple recording protocol

1. Pick a physical activity with clear movement (walking, jogging, cycling, etc.).
2. Fix the phone in a consistent location such as a trouser pocket or armband. Note the body part and orientation.
3. Start the app recording **before** you start moving.
4. Perform the activity for **at least 5 minutes**. Note approximately when you pause, speed up, turn or restart.
5. Stop immediately after finishing.
6. Export raw accelerometer readings as **CSV** to your computer. Keep the original export unchanged. Copy it to this project directory and name the copy \`sensor_raw.csv\` (rename filename only; do not edit rows or values).
7. Keep your personal recording notes for the first notebook markdown cell.

## Check your CSV

Expected fields: a timestamp or time column and 3 axes of acceleration, ax, ay, az. Actual headings vary by app. Your units might be **m/s²** or **g**, and timestamp units may be seconds or milliseconds. Check the app or CSV documentation.

- If acceleration is in **g**, set \`ACCEL_UNITS = "g"\` in the notebook for conversion to m/s².
- If raw numeric timestamps are in **milliseconds**, set \`TIME_UNIT = "ms"\`.
- If the notebook cannot detect column names, inspect the CSV header and set \`COLUMN_OVERRIDES\` to exact column names.
- The notebook uses the measured effective sampling rate and creates \`sensor_clean.csv\` without changing the raw file.

## Keep original data safe

This GitHub repository is **public**. Raw exports can include GPS tracks and other personal data; leave CSV files ignored by Git. Submit the original \`sensor_raw.csv\` with the completed \`laba_<lastname>.ipynb\` through Canvas. The instructor may ask a short oral question, so make sure you can explain your own graphs and anomalies.
