# Lab A — Sensor Data Analysis for Sports

CM2023/HI1033 · HT26 · KTH

This repository contains a **starter** Jupyter Notebook for Lab A. It follows the supplied seven-page Lab A instructions. **No real sensor data has been collected or analyzed yet.** Do not submit the notebook with TODOs or missing outputs.

## Project files

| File | Role |
|---|---|
| \`laba_lastname.ipynb\` | Main lab report in Jupyter Notebook (rename LASTNAME to your actual surname before submission) |
| \`requirements.txt\` | Python package dependencies |
| \`RECORDING_GUIDE.md\` | Phone recording and CSV export guide |
| \`.gitignore\` | Excludes private raw data and generated files |
| \`sensor_raw.csv\` | **Not created yet**. You generate this file by recording a real activity (at least 5 minutes) |

## Walking recording received — start here

The user's walking session was recorded on 2026-11-17 (~9 min 17 sec, median sampling frequency ~50.1 Hz). **The raw CSV is not committed** because this GitHub repository is public. Copy the unmodified uploaded **TotalAcceleration.csv** to a local file named **sensor_raw.csv** before running the notebook.

**Use [VS_CODE_SETUP.md](VS_CODE_SETUP.md) for step-by-step Visual Studio Code instructions.** The notebook's time and axis mapping is already configured for this export: seconds_elapsed, x, y, z.

## Setup before recording

1. Install Python 3.10+ and Git. Clone this repository:

   \`\`\`bash
   git clone https://github.com/aabdly1-dot/LabA-Sensor-Analysis.git
   cd LabA-Sensor-Analysis
   \`\`\`

2. Create a virtual environment:

   \`\`\`bash
   python -m venv .venv
   \`\`\`

3. Activate it (Windows PowerShell: \`.\.venv\Scripts\Activate.ps1\`; macOS/Linux: \`source .venv/bin/activate\`), then install:

   \`\`\`bash
   python -m pip install -r requirements.txt
   \`\`\`

4. Start Jupyter:

   \`\`\`bash
   python -m notebook
   \`\`\`

5. Open \`laba_lastname.ipynb\`. **Do not run the data-loading cell until you have recorded data.** Without sensor_raw.csv, it intentionally stops with a helpful FileNotFoundError.

## After recording

1. Follow \`RECORDING_GUIDE.md\` to export the original CSV. Rename its *filename only* to \`sensor_raw.csv\` and put it next to the notebook (do not alter its content).
2. Enter real session notes in the first notebook markdown cell.
3. Inspect the CSV column names and units. In the notebook, set \`ACCEL_UNITS = "g"\` only if the sensor exports acceleration in g; keep \`"m/s2"\` for m/s². Adjust \`COLUMN_OVERRIDES\` and \`TIME_UNIT\` if necessary.
4. In Jupyter, select **Run All Cells**. Review the cleaned data, anomaly clusters and plots.
5. Replace *every* TODO with your own interpretations, a real peer-reviewed study, a product comparison, and a 150–250-word reflection.
6. Run all cells again, save with visible outputs, and rename the notebook \`laba_<your_actual_lastname>.ipynb\`.

**Privacy:** This is a public GitHub repository. Some sensor exports may contain exact GPS coordinates or personally identifying information. The raw and cleaned CSVs are excluded from Git by default. Keep them locally and submit them privately through the course submission system, rather than publishing them by accident. Also check notebook outputs before pushing.

## What to submit (Canvas)

1. \`sensor_raw.csv\` — original, unmodified sensor export.
2. \`laba_<lastname>.ipynb\` — executed notebook, code and outputs visible, runs top to bottom without errors.

No separate Word/PDF report. **Deadline: check Canvas.** There may be an oral question about your data, especially physical interpretation of anomalies or movement frequencies.

## Pass checklist

- [ ] At least five minutes of authentic sensor data at approximately 50 Hz, phone position fixed
- [ ] Sport, session details, rate, notable events documented
- [ ] Data loaded; shape, types, examples and effective sampling rate inspected
- [ ] At least one justified cleaning operation
- [ ] Descriptive statistics table and IQR anomaly detection
- [ ] Physical explanation for each anomaly cluster
- [ ] Three Python plots, all with titles/axis labels, each followed by 2–4 interpretation sentences
- [ ] Peer-reviewed study cited APA; all three comparison questions answered
- [ ] Commercial device/app sensors, metrics, available exports and research gap evaluated
- [ ] 150–250-word reflection
- [ ] Both required files submitted, executed notebook verified

Reference: the supplied **Lab A – Sensor Data Analysis for Sports (HT26)** course handout.
