# EEG Research Analyzer

An open-source Windows application for EEG band-power analysis and before/after comparison.

The tool is designed to make EEG analysis easier for researchers and study participants who may not be comfortable working with programming tools or command-line software.

## Features

* Simple Windows graphical interface
* Select EEG files using a file browser
* Before/after EEG comparison
* EEG band-power analysis
* Delta: 0–4 Hz
* Theta: 4–8 Hz
* Alpha: 8–13 Hz
* Beta: 13–30 Hz
* Sampling frequency support including 256 Hz EEG recordings
* Comparison of before and after band power
* Percentage change for each frequency band
* Publication-quality comparison chart
* Excel (`.xlsx`) output
* PNG comparison chart
* Combined PDF report
* Participant name included in generated output files
* Reset functionality for processing another participant/session
* Standalone Windows executable; Python is not required for the Windows release

## Intended Use

This software is intended for EEG research, exploratory analysis, and comparison of EEG recordings collected before and after an intervention, activity, or experimental condition.

One potential research application is the study of changes in EEG band power associated with practices such as meditation, relaxation exercises, or Hasta Mudra.

## Important

This software is a research and analysis tool.

It is **not a medical diagnostic device**, does not provide a clinical diagnosis, and should not be used as a substitute for interpretation by a qualified healthcare or neuroscience professional.

Results should be interpreted in the context of the EEG acquisition equipment, electrode/sensor configuration, recording conditions, preprocessing methodology, and research protocol.

## EEG Channels

The current research configuration is designed to support EEG recordings containing channels such as:

* PF1
* PF2
* FF1
* FF2
* VC
* Cz
* T3
* T4

Channel availability depends on the source EEG recording.

## Output

The application generates:

### Excel

A structured `.xlsx` file containing the calculated EEG band-power results and before/after comparison.

### PNG

A high-resolution comparison chart showing:

* Before power
* After power
* Exact power values
* Percentage change for Delta, Theta, Alpha, and Beta

### PDF

A combined report containing:

* EEG analysis information
* Band-power summary
* Before values
* After values
* Percentage change
* Interpretation summary

## Basic Workflow

1. Launch `EEG-Research-Analyzer-Windows.exe`.
2. Enter the participant/research subject name.
3. Select the **Before** EEG recording.
4. Select the **After** EEG recording.
5. Click **Start Analysis**.
6. Wait for processing to finish.
7. Review the generated Excel, PNG, and PDF files.
8. Use **Reset** to analyze another recording pair.

## Input Data

The application is intended for EEG recordings exported from compatible EEG acquisition systems.

Supported input formats depend on the version of the application and the underlying EEG reader.

EDF is the primary supported interchange format.

Raw `.eeg` files are device/software dependent and are not a single universal EEG format. For `.eeg` recordings, the associated format metadata may be required.

## Methodology

The analysis calculates power spectral density and integrates spectral power within predefined EEG frequency bands.

The current frequency bands are:

| Band  | Frequency |
| ----- | --------: |
| Delta |    0–4 Hz |
| Theta |    4–8 Hz |
| Alpha |   8–13 Hz |
| Beta  |  13–30 Hz |

Gamma is intentionally excluded from the current analysis configuration.

The exact preprocessing and analysis implementation should be reviewed before using results in a formal scientific publication.

## Research Reproducibility

For publication-quality research, investigators should document:

* EEG acquisition equipment
* Sampling frequency
* Electrode/sensor configuration
* Reference configuration
* Recording duration
* Recording environment
* Preprocessing steps
* Filtering parameters
* Artifact handling
* Spectral estimation method
* Frequency-band definitions
* Statistical analysis methodology

## Privacy

Do not upload identifiable EEG recordings, participant information, medical records, or other sensitive research data to this repository.

The repository is intended to contain software, documentation, and non-sensitive examples only.

## License

This project is released under the MIT License.

See [LICENSE](LICENSE).

## Status

This project is under active development.

The software should be considered a research tool rather than a clinically validated medical application.