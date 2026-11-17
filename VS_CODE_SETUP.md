# Open your walking analysis in Visual Studio Code

Your four exported files were inspected. The main analysis uses **TotalAcceleration.csv**, which contains x, y, z (m/s²) and \`seconds_elapsed\`. The other CSVs are optional supporting recordings. The actual sensor export is deliberately **not uploaded to public GitHub**.

## 1. Open the GitHub project on your computer

1. Install [Visual Studio Code](https://code.visualstudio.com/) and Python 3.10+.
2. In VS Code, install the **Python** and **Jupyter** extensions (the repo recommends both).
3. Open a VS Code terminal (Terminal → New Terminal), then run:

\`\`\`bash
git clone https://github.com/aabdly1-dot/LabA-Sensor-Analysis.git
cd LabA-Sensor-Analysis
code .
\`\`\`

If you already cloned the repository, use \`git pull\` inside the project folder instead of cloning again.

## 2. Create a Python environment

Windows PowerShell:

\`\`\`powershell
py -3 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
\`\`\`

macOS/Linux:

\`\`\`bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
\`\`\`

If PowerShell blocks activation, select \`.venv\` as the notebook's Python kernel in VS Code and run \`.\.venv\Scripts\python.exe -m pip install -r requirements.txt\` in the terminal.

## 3. Add your real walking CSV locally

Your uploaded files are:
- \`TotalAcceleration.csv\` — chosen for the lab's acceleration-magnitude analysis
- \`Accelerometer.csv\` — gravity-compensated acceleration (different signal)
- \`AccelerometerUncalibrated.csv\` — alternate raw export
- \`Metadata.csv\` — technical recording details; **contains a device identifier: do not publish**

On your own computer, put an **unchanged copy** of \`TotalAcceleration.csv\` in this project and name the copy \`sensor_raw.csv\`. You can leave the original filename too. This notebook reads \`sensor_raw.csv\`. Don't open and save/reformat the raw CSV in Excel.

**Never force-add raw CSVs to GitHub.** The repository is public and CSVs are ignored in \`.gitignore\`. Submit \`sensor_raw.csv\` privately to Canvas along with your completed notebook.

## 4. Run the Python notebook in VS Code

1. Open \`laba_lastname.ipynb\`.
2. At the top right, choose **Select Kernel** → Python Environments → your project \`.venv\`.
3. Click **Run All**.
4. You should see: a descriptive-statistics table, effective sampling rate, recording-gap details, IQR anomaly clusters, and three figures.
5. If the notebook reports missing data, check the copy is in the **same folder** as the notebook and called \`sensor_raw.csv\`.

## 5. What the uploaded recording already shows

These are checks from the original uploaded file, **not invented measurements**:

- Data source: \`TotalAcceleration.csv\` with 25,510 rows
- Time span: ~557.36 seconds (9 min 17 sec) with some recording gaps
- Median sample interval: ~0.01996 sec, effective ~50.10 Hz
- No missing x/y/z/time values
- 7 timestamp gaps > 0.05 seconds, including a gap of ~17.45 seconds
- 1-second edge trim in notebook leaves 25,410 rows
- IQR method after edge trim flags 18 samples in 10 clusters at a 2-second grouping threshold

**Important:** Some gaps may mean the phone was not recording continuously. You need to describe that honestly. Unusual acceleration samples can be real walking/handling motion; the notebook cannot know the physical cause without your notes.

## 6. Finish your submission

The notebook is code-ready but contains required written TODOs: exactly where you carried the phone, any real stop/fast-walk events, justifications for cleaning/anomalies, **2–4 sentences below each of the three plots**, a real peer-reviewed walking/accelerometer study in APA format with its three comparisons, a verified commercial-product comparison, and a **150–250 word reflection**. Also rename \`laba_lastname.ipynb\` using your actual last name before submitting.

Save your notebook with all code cells executed and outputs visible. Submit \`sensor_raw.csv\` and \`laba_<your_lastname>.ipynb\` through Canvas.
