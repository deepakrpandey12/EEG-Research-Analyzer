# EEG Research Analyzer

A standalone Windows application for EEG band-power analysis and before/after comparison.

The EEG Research Analyzer is designed to make EEG spectral analysis accessible to researchers and users who do not want to work with Python, command-line tools, or complex software environments.

The application analyzes EEG recordings, calculates power within commonly used EEG frequency bands, compares Before and After recordings, and produces Excel, PNG, and PDF outputs.

---

## Features

- Simple graphical user interface
- Standalone Windows executable
- No Python installation required for the Windows release
- Select EEG recordings using a file browser
- Before and After EEG comparison
- EEG band-power analysis
- Exact band-power values in the generated results
- Percentage change between Before and After recordings
- Comparison visualization
- High-resolution PNG comparison figure
- Excel (`.xlsx`) results
- Combined PDF report
- Participant/research subject name included in output filenames
- Reset functionality for processing another recording pair
- Designed for research and exploratory EEG analysis

---

## EEG Frequency Bands

The current analysis uses the following frequency bands:

| Band | Frequency Range |
|---|---:|
| Delta | 0–4 Hz |
| Theta | 4–8 Hz |
| Alpha | 8–13 Hz |
| Beta | 13–30 Hz |

Gamma is intentionally excluded from the current analysis.

The frequency-band definitions can be modified in the underlying analysis software if a different research protocol requires different definitions.

---

## EEG Acquisition

The current research configuration is intended for EEG recordings collected at a sampling frequency of **256 Hz**.

The electrode/sensing points used in the research configuration include:

- PF1
- PF2
- FF1
- FF2
- VC
- Cz
- T3
- T4

Actual channel availability depends on the EEG acquisition equipment and the source recording.

---

# Getting Started

## Windows Application

A standalone Windows executable is available from the project's GitHub Releases page:

**EEG Research Analyzer Releases**

https://github.com/deepakrpandey12/EEG-Research-Analyzer/releases

The Windows release does not require Python or other programming software to be installed.

### Basic workflow

1. Download `EEG-Research-Analyzer-Windows.exe` from the Releases page.
2. Complete the Windows first-time security setup described below if required.
3. Launch the application.
4. Enter the participant/research subject name.
5. Select the **Before** EEG recording.
6. Select the **After** EEG recording.
7. Verify that the selected file paths are displayed in the application.
8. Click **Start Analysis**.
9. Wait for processing to complete.
10. Review the generated Excel, PNG, and PDF results.
11. Click **Reset** when you want to process another recording pair.

No command-line interaction is required for normal use.

---

# Windows Security — First-Time Setup

Because the Windows executable is downloaded from the internet, Windows may mark it as coming from another computer.

If Windows blocks the application:

1. Locate `EEG-Research-Analyzer-Windows.exe`.
2. Right-click the file.
3. Select **Properties**.
4. In the **General** tab, look near the bottom of the window.
5. If an **Unblock** option is available, check it.
6. Click **Apply**.
7. Click **OK**.
8. Launch the application.

This normally only needs to be done once for a downloaded copy of the application.

### Windows SmartScreen

Windows may also display a message such as:

> Windows protected your PC

This can occur because the application is an independently distributed executable and is not commercially code-signed.

If you obtained the executable from the official project Releases page, Windows may allow you to proceed using:

**More info → Run anyway**

Only run executables obtained from the official project repository or another source that you trust.

---

# Input Data

The primary EEG interchange format supported by the application is **EDF (European Data Format)**.

The application is intended for EEG recordings exported from compatible EEG acquisition systems.

### About `.eeg` files

The `.eeg` file extension is not a single universal EEG data format.

Different EEG manufacturers and software systems can use `.eeg` for different underlying data structures. Some `.eeg` recordings require additional header or metadata files to correctly interpret the recording.

Therefore, compatibility with a particular `.eeg` file depends on the format produced by the recording system.

If an `.eeg` file cannot be opened, it may need to be exported from the original EEG software into EDF or another supported interchange format.

---

# Analysis Method

The application performs frequency-domain analysis of the EEG signal.

The general processing workflow includes:

1. Reading the EEG recording.
2. Identifying the available EEG channels.
3. Obtaining the recording sampling frequency.
4. Signal preprocessing.
5. Spectral power estimation.
6. Calculation of power within the predefined frequency bands.
7. Calculation of Before and After summary values.
8. Calculation of percentage change.
9. Generation of graphical and report outputs.

Power spectral density is estimated using Welch's method, and band power is calculated by integrating spectral power across the relevant frequency range.

The exact implementation is contained in the software source code associated with the project.

---

# Before vs After Comparison

When Before and After recordings are available, the application calculates:

- Before band power
- After band power
- Absolute difference
- Percentage change

The comparison visualization presents Before and After values side by side for:

- Delta
- Theta
- Alpha
- Beta

The exact numerical values are displayed on the figure so that differences can be read without estimating values from bar height alone.

Percentage changes are displayed separately between the frequency-band groups to improve readability.

---

# Output

The application produces three primary research outputs.

## 1. Excel Workbook

The `.xlsx` file contains structured EEG band-power results.

The workbook may include:

- Participant/research subject name
- EEG channel information
- Frequency-band power
- Before results
- After results
- Comparison values
- Percentage change

The Excel workbook is intended to provide numerical results that can be further reviewed or analyzed by the researcher.

---

## 2. PNG Comparison Figure

The PNG output provides a visual Before vs After comparison.

The figure includes:

- Delta Before and After
- Theta Before and After
- Alpha Before and After
- Beta Before and After
- Exact power values
- Percentage change for each frequency band

The figure is generated at high resolution for use in research documentation and presentations.

---

## 3. PDF Report

The PDF combines the principal analysis results into a single report.

The report includes:

- Analysis information
- Band-power summary
- Before values
- After values
- Percentage change
- Interpretation summary
- EEG frequency-band information

The band-power summary is presented as a table rather than as raw dataframe output.

The report is designed to provide a convenient human-readable summary of the analysis.

---

# Interpretation

Changes in EEG band power should be interpreted carefully.

An increase or decrease in the power of a particular frequency band does not, by itself, establish a specific psychological, neurological, physiological, or clinical effect.

EEG measurements can be affected by factors including:

- Electrode placement
- Reference configuration
- Electrode impedance
- Movement
- Muscle activity
- Eye movements
- Recording environment
- Participant state
- Drowsiness
- Equipment characteristics
- Signal preprocessing
- Recording duration
- Individual variability

The generated percentage changes are descriptive comparisons between the recordings and should not automatically be interpreted as evidence of causation.

---

# Research Use

This software is intended for:

- EEG research
- Exploratory EEG analysis
- Before/After EEG comparisons
- Research involving meditation or relaxation practices
- Experimental interventions
- Academic and scientific investigations

One potential research application is studying changes in EEG band power associated with practices such as meditation, relaxation exercises, or Hasta Mudra.

The software does not determine whether an intervention caused an observed EEG change.

---

# Important Research Considerations

For reproducible scientific research, investigators should document the following:

- EEG acquisition equipment
- Sampling frequency
- Electrode/sensing locations
- Reference configuration
- Recording duration
- Recording environment
- Participant state
- Preprocessing procedure
- Filtering parameters
- Artifact handling
- Spectral estimation method
- Frequency-band definitions
- Statistical analysis
- Number of participants
- Experimental protocol

Results generated by this software should be evaluated together with the complete experimental methodology.

---

# Clinical Disclaimer

This software is a **research and analysis tool**.

It is **not a medical diagnostic device** and does not provide a medical diagnosis, treatment recommendation, or clinical assessment.

The results should not be used as a substitute for interpretation by a qualified healthcare, neuroscience, EEG, or other appropriately trained professional.

No claim of clinical effectiveness or clinical validity is made by this project.

---

# Data Privacy

EEG recordings may contain sensitive research or participant information.

**Do not upload identifiable EEG recordings or other sensitive participant data to this public GitHub repository.**

The public repository is intended for:

- Software
- Documentation
- Source code
- Non-sensitive examples
- Publicly shareable research materials

Participant data and research recordings should be stored according to the applicable research protocol, institutional requirements, and data-protection requirements.

---

# Reproducibility

For research intended for publication, investigators should retain the original EEG recordings and document the complete acquisition and analysis procedure.

The software output should be considered one component of the overall research workflow.

When reporting results, researchers should provide sufficient methodological information for other researchers to understand and reproduce the analysis.

---

# Project Status

**Version:** 1.0.0

This project is provided as an open-source research tool.

The current release provides a standalone Windows application for EEG band-power analysis and Before/After comparison.

Future changes are not guaranteed. The current release should be treated as a stable standalone research utility rather than a continuously maintained commercial software product.

---

# Download

The latest Windows executable is available from:

https://github.com/deepakrpandey12/EEG-Research-Analyzer/releases

Current Windows release:

**EEG-Research-Analyzer-Windows.exe**

SHA-256:

`00f8bee03c7cd45b771324a3db458d03cf1608b764c4f5f221cb1268ec7f7cc9`

The SHA-256 checksum can be used to verify that the downloaded executable matches the published release.

---

# License

This project is released under the **MIT License**.

See the [LICENSE](LICENSE) file for the complete license text.

---

# Acknowledgement

This project was developed to provide a simple and accessible tool for EEG research and analysis.

Users are encouraged to independently validate the analysis methodology and results against the requirements of their particular research protocol and EEG acquisition system.