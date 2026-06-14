# Arrhythmia Diagnosis

ECG arrhythmia classification data pipeline using the [MIT-BIH Arrhythmia Database](https://physionet.org/content/mitdb/1.0.0/) (48 subjects, PhysioNet).

Built as part of my BSc Computer Science degree at Brunel University.

## Pipeline

Raw WFDB recordings → HDF5 conversion → Butterworth bandpass filter (0.5–40 Hz, order 5) → z-score normalisation → 500-sample segmentation → multi-label binary encoding

## Arrhythmia classes

Normal, Atrial, Ventricular, Junctional, Fusion, Paced, Noise/Artifact

## Stack

Python, [wfdb](https://github.com/MIT-LCP/wfdb-python), scipy, h5py, scikit-learn, NumPy

## Usage

Place MIT-BIH `.dat` and `.atr` files in `Data/OriginalECGs/`, then:

```bash
pip install wfdb scipy h5py scikit-learn numpy
python main.py
```

Outputs segmented, normalised HDF5 files ready for model training.
