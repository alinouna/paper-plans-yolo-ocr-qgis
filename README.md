# Digitalisation de plans papier vers QGIS (YOLOv8 + OCR)

> **🔒 The source code in this repository is encrypted.**
> The archive `yolo-ocr-digitization.zip` is protected with **WinZip AES-256** encryption.
> The password is shared privately with recruiters / reviewers on request.

## What it does

Pipeline de digitalisation automatique de plans papier géoréférencés en shapefiles.

- **Détection des chambres** : YOLOv8 entraîné sur un dataset synthétique augmenté (Albumentations, 33 zones) ; alternative par transformée de Hough filtrée par OCR.
- **OCR et géoréférencement** : numéros et types de chambre (Tesseract, EasyOCR) ; conversion pixel → coordonnées monde (`rasterio`) et export shapefile.

## Results

- Réduction majeure du temps de saisie manuelle.
- Création de données SIG directement exploitables sous QGIS.

## Stack

Python · OpenCV · YOLOv8 (Ultralytics) · Albumentations · Tesseract · EasyOCR · geopandas · rasterio · shapely

## Decrypt & run

```bash
pip install pyzipper
python3 decrypt.py          # prompts for the password, extracts to ./src
# or without the helper (7-Zip / WinZip / unzip all support AES-256):
7z x yolo-ocr-digitization.zip -p
```

## Integrity

Every file inside the archive is listed with its SHA-256 in `MANIFEST.sha256`.
Verify **from the repository root** (the paths are relative to it):

```bash
sha256sum -c MANIFEST.sha256      # Linux / macOS / Git Bash
certutil -hashfile src\main.py SHA256   # Windows, per file
```

---
*Ali Nouna — alinouna@gmail.com — linkedin.com/in/AliNouna*
