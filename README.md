# ECG Asystole Detection

A Python-based implementation for detecting asystole in ECG signals using signal processing techniques.

## Overview

This project implements an asystole detection function that analyzes ECG signals to identify periods where the heart stops beating. Asystole is defined as the absence of the QRS complex for at least 4 seconds, which is a critical medical emergency requiring immediate intervention.

## Features

- **ECG Signal Preprocessing**: Implements noise reduction and signal enhancement techniques
- **Fourier Transform Analysis**: Frequency domain analysis to identify dominant signal components
- **Bandpass Filtering**: Removes both low-frequency baseline wander and high-frequency noise (5-50 Hz)
- **Real-time Detection**: Sliding window algorithm for continuous asystole monitoring
- **Visual Analysis**: Comprehensive visualization tools for both time and frequency domain analysis

## Technical Approach

### Signal Processing Pipeline

1. **Data Loading**: Reads ECG data from CSV format (sampling rate: 250 Hz)
2. **Fourier Transform**: Applies FFT to analyze frequency components and identify noise sources
3. **Bandpass Filtering**: Filters signal to preserve relevant cardiac frequencies (5-50 Hz) while removing:
   - Low-frequency baseline wander (< 5 Hz)
   - High-frequency noise from powerline interference and muscle activity (> 50 Hz)
4. **Asystole Detection**: Uses a sliding window approach with statistical analysis to detect QRS absence

### Detection Algorithm

The asystole detection function employs:
- **Sliding Window**: 4-second windows with 1-second step size
- **Feature Extraction**: Standard deviation calculated for each window
- **Adaptive Thresholding**: Threshold determined from baseline healthy rhythm
- **Alarm Generation**: Binary alarm array indicating asystole presence

## Implementation

The notebook includes:
- Raw ECG signal visualization and inspection
- Frequency domain analysis with linear and logarithmic scales
- Comparative analysis of raw vs. filtered signals
- Complete asystole detection implementation with performance metrics
- Detailed explanations and scientific references

## Dependencies

```python
- numpy
- pandas
- scipy
- matplotlib
```

## Usage

Open the Jupyter notebook `ECG_Asystole_Detection.ipynb` and run the cells sequentially. The notebook processes ECG data and demonstrates:

- Signal preprocessing techniques
- Frequency analysis visualization
- Filter design and implementation
- Asystole detection with timing information

## Key Results

The implementation successfully:
- Identifies dominant frequency components in ECG signals
- Removes noise while preserving critical cardiac features
- Detects asystole onset with precise timing
- Provides visual confirmation of detection accuracy

## References

The implementation is based on established signal processing techniques and cardiac monitoring standards documented in biomedical signal processing literature.