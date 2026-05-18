# AI-Based QR Code Detection

This feature adds an AI-enabled QR code detection and quishing prevention system that can detect QR codes from images, decode embedded URLs, extract URL-based features, and classify suspicious links.

## Features

- Detect QR codes in images using OpenCV and Pyzbar
- Decode QR payloads and extract embedded URLs or data
- Analyze URL features for phishing and suspicious patterns
- Train a supervised classifier on URL data using scikit-learn
- Provide risk scoring and safety warnings before opening links
- Includes a sample pipeline and smoke-test utilities

## Folder structure

- `qr_detection.py` — QR code detection and decoding utilities
- `url_features.py` — URL feature extraction for phishing classification
- `model.py` — classifier training, prediction, and persistence
- `train.py` — command-line training script
- `utils.py` — dataset loading and metric evaluation
- `tests/test_qr_detection.py` — basic unit tests
- `requirements.txt` — dependencies

## Usage

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Detect QR codes in an image:

```bash
python qr_detection.py --image path/to/qr_image.png
```

3. Train the classifier on a CSV dataset of labeled URLs:

```bash
python train.py --data_csv data/qr_url_labels.csv --model_path qr_risk_model.joblib
```

4. Predict risk for a decoded URL:

```bash
python model.py --predict "http://example.com"
```

## Notes

- This implementation uses classical ML for URL classification. It can be extended with NLP or deep learning models for richer phishing detection.
- For live camera support, use the `scan_live_camera` function in `qr_detection.py`.
- If you want to add this feature to the repo, keep it as a self-contained folder and follow the contribution guidelines in the root `CONTRIBUTING.md`.
