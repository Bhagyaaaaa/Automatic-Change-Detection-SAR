Automatic Change Detection in SAR Satellite Images
A Python-Based Application for Detecting Surface Changes Using Sentinel-1 SAR Imagery
<br>
📌 Overview

This project implements an end-to-end Automatic Change Detection System for SAR (Synthetic Aperture Radar) satellite images.
Using pre-event and post-event SAR images, the application:

✔ Preprocesses (filters, aligns, normalizes)
✔ Applies change-detection algorithms
✔ Generates a binary change map
✔ Calculates changed area
✔ Visualizes outputs using matplotlib
✔ Provides a simple Tkinter GUI for non-technical users

This system is useful for:

Flood mapping

Deforestation monitoring

Urban expansion

Disaster assessment

Environmental change tracking


<br>
🚀 Features
🖥️ Application

Tkinter-based GUI

Non-freezing UI using multithreading

Easy load → process → analyze workflow

🔍 Functionality

Load pre & post SAR GeoTIFF images

Automatic preprocessing:

Speckle filtering (Median / Lee)

Radiometric normalization

Co-registration check

Multiple change detection techniques:

Log-Ratio (default & best for SAR)

Ratio Image

Image Differencing

Change Vector Analysis (CVA)

PCA-based detection

Automatic thresholding:

Otsu

K-Means

📊 Outputs

Change mask (GeoTIFF, PNG)

Before/After image previews

Histogram of change metric

Pie chart: Changed vs Unchanged

Summary JSON:

Total area

Changed area

Percent change

🛠️ Project Structure
SAR-Change-Detection/
│── app.py                 # Main GUI application  
│── data_fetch.py          # Load or download sample SAR images  
│── preprocess.py          # Filtering, normalization, alignment  
│── change_detector.py     # Core change detection algorithms  
│── postprocess.py         # Morphological cleanup + area estimation  
│── analyzer.py            # Visualization utilities  
│── utils.py               # Helper functions  
│── samples/               # Sample SAR images (optional)  
│── outputs/               # Saved results (masks, charts, summary)  
│── requirements.txt  
│── README.md  

📥 Requirements & Installation
1. Install Dependencies
pip install -r requirements.txt


requirements.txt

numpy
opencv-python
matplotlib
rasterio
scikit-image
scikit-learn
scipy
tqdm
tk

2. Optional (For automatic Sentinel-1 download)
pip install sentinelsat

▶️ How to Run the Application

Clone the repository:

git clone https://github.com/yourusername/SAR-Change-Detection.git
cd SAR-Change-Detection


Run the app:

python app.py

In the GUI:
📥 Step 1 — Load Images

Load Pre-Event Image

Load Post-Event Image

(Optional: download sample Sentinel-1 pair)

⚙️ Step 2 — Start Processing

Automatic preprocessing

Apply change detection

Generates change image

📊 Step 3 — Analyze

Shows before/after visuals

Shows change mask

Histogram & Pie chart

💾 Step 4 — Export

Exports:

change_mask.tif

change_mask.png

summary.json

🧠 How It Works (Simple Explanation)
1️⃣ Preprocessing

SAR images contain speckle noise, so the system applies:

Radiometric calibration / normalization

Speckle filtering (Median / Lee filter)

Alignment check (co-registration)

Optional conversion to dB scale

2️⃣ Change Metric

Example: Log-Ratio

log_ratio = log(post) - log(pre)

3️⃣ Thresholding

Otsu is used to separate changed vs unchanged pixels.

4️⃣ Post-Processing

Remove tiny objects

Morphological operations

Compute area changed

5️⃣ Visualization

Generates charts and preview images.

📊 Example Output
Summary (summary.json)
{
  "method": "log-ratio + otsu",
  "changed_pixels": 15234,
  "total_pixels": 80000,
  "changed_area_m2": 925000.0,
  "percent_changed": 19.04
}

Visuals Produced

Before image

After image

Change mask

Histogram

Pie chart

📁 Sample Dataset

Use publicly available SAR data:
Sentinel-1 GRD (free, open)
Download from:

Copernicus Open Access Hub

Alaska Satellite Facility (ASF DAAC)

SentinelSat script (optional in project)

🧩 Extensions (Optional)

Deep learning: U-Net segmentation

Multi-temporal change detection

Coherence-based change detection (using SLC data)

Web-based dashboard using Streamlit

📜 License

MIT License.
Free to use & modify for academic or personal projects.

🛰️ Contributors

Feel free to submit pull requests or open issues!
