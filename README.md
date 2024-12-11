# Mental Workload Analysis using EEG Data

## Overview
This project analyzes mental workload during different cognitive tasks using EEG data collected from both the Emotiv and Neurosky MindWave headsets. The analysis includes attention levels, meditation states, signal quality, and task performance metrics across various cognitive tasks and difficulty levels.

## Data Collection
### EEG Hardware
- **Emotiv Headset**: Used for collecting high-quality EEG data with multiple channels
- **Neurosky MindWave**: Used for collecting attention and meditation metrics

The dual-headset approach provides complementary data:
- Emotiv provides detailed multi-channel EEG recordings
- Neurosky provides processed metrics for attention and meditation states

### Task Types
- `Cal`: Calculation
- `Lin`: Linguistic
- `Fin`: Finger Tapping
- `Rot`: Mental Rotation

[Rest of the README remains the same as before...]

## Data Structure
The data is organized in MATLAB (.mat) files with the following naming convention:
```
[TaskType]_[Subject]_L[Difficulty]T[Trial].mat
```

### Parameters
- `Subject`: Subject identifier code (20 subjects total)
- `Difficulty Level`:
  - `l`: low
  - `m`: middle
  - `h`: high
- `Trial`:
  - `1`: Practice Round
  - `2-6`: Experimental Rounds

### Data Fields
#### Behavioral Data
- `Rating`: Subjective Difficulty Rating after 5 trials
- `keyPressed`: Answer from subject
- `keyT`: Timestamp when the key was pressed
- `keyT_i`: Corresponding location in EEG when the key was pressed
- `imageT`: Timestamp when the question image was shown
- `imageT_i`: Corresponding location in EEG when the question image was shown
- `CorrectAns`: 1 for correct, 0 for wrong answer

#### EEG Data
##### Emotiv Data
- Raw EEG data from multiple channels
- High-resolution temporal data
- Channel-specific signal quality indicators

##### Neurosky MindWave Data
- `raw`: EEG raw data
- `attention`: Attention level
- `meditation`: Meditation level
- `PQ`: Signal quality

## Installation

### Requirements
```bash
pip install numpy pandas scipy plotly matplotlib
```

### Directory Structure
```
project_root/
│
├── ASM/                    # Data directory
│   ├── Cal_ASM_LhT1.mat
│   ├── Lin_ASM_LhT1.mat
│   ├── ...
│   └── visualizations/    # Generated visualizations
└── README.md
```

## Usage

### Running the Analysis
```python
# Import required modules
from analysis import process_all_files

# Process all files and generate individual visualizations
process_all_files("ASM")
```

### Creating the Dashboard
```python
# Import dashboard creation module
from dashboard import create_dashboard

# Create and display the interactive dashboard
fig = create_dashboard("ASM")
fig.show()
```

## Visualization Features

### Individual Trial Visualizations
- Attention levels over time
- Meditation levels over time
- Signal quality monitoring
- Response times and accuracy
- Event markers for image presentations

### Dashboard Components
1. **Task Performance Analysis**
   - Response time distributions
   - Accuracy rates by task type
   - Performance across difficulty levels

2. **EEG Metrics Visualization**
   - Attention and meditation patterns
   - Signal quality monitoring
   - Event-related changes

3. **Statistical Summaries**
   - Mean and standard deviation of metrics
   - ANOVA results across difficulty levels
   - Performance comparisons between tasks

## Output Examples
The analysis generates two types of outputs:

1. Individual HTML files for each trial in `ASM/visualizations/`
2. A comprehensive dashboard (`dashboard.html`) combining all analyses

## Contributing
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Citation
If you use this code in your research, please cite:
```
@misc{mental_workload_analysis,
  author = {Santosh Srinivasaiah, Prathiksha, Prathwik, Shafat, Ujwal},
  title = {Mental Workload Analysis using EEG Data},
  year = {2024},
  publisher = {GitHub},
  url = {https://github.com/braincomputingsantosh/EEG-Mental-Workload-Interactive}
}
```

## Contact

Project Link: [https://github.com/braincomputingsantosh/EEG-Mental-Workload-Interactive](https://github.com/braincomputingsantosh/EEG-Mental-Workload-Interactive)
