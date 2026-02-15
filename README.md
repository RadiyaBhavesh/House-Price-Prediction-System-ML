# 🏠 House Price Prediction (Streamlit App)

A Machine Learning-based house price prediction app built with Streamlit.

It predicts prices using:
- Location
- Area (sqft)
- BHK
- Bathrooms

---

## ✨ Features
- 📍 Gujarat location-based prediction
- 🧠 Hybrid model (Linear Regression + Random Forest)
- 📊 Confidence and expected range display
- 💡 Budget-zone recommendation
- 🗺️ Interactive map support

---

## 📁 Project Structure
- `app/app.py` – Streamlit application
- `Dataset/gujarat_house_price_.csv` – Training dataset
- `Model/model_train.py` – Offline model training script
- `Model/*.pkl` – Model artifacts (may be Git LFS pointers in cloud builds)
- `render.yaml` – Render deployment configuration

---

## ⚙️ Local Setup

```bash
git clone <your-repo-url>
cd House-Price-Prediction-System-ML
pip install -r requirements.txt
streamlit run app/app.py
```

---

## 🚀 Render Deployment (Fresh)

This project now supports fresh Render deploys even when `.pkl` model files are missing or unresolved due to Git LFS.

### Option A: Blueprint deploy (recommended)
1. Push this repo to GitHub.
2. In Render: **New +** → **Blueprint**.
3. Select the repository.
4. Render uses `render.yaml` automatically.

### Option B: Manual Web Service
- **Environment:** Python
- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `streamlit run app/app.py --server.address 0.0.0.0 --server.port $PORT`

### Why this works
On startup, the app checks whether model files are available and valid.
If not, it trains models from `Dataset/gujarat_house_price_.csv` and continues booting.

---

## 🧠 Model Notes
- Linear Regression + StandardScaler
- Random Forest Regressor
- Hybrid prediction logic in app runtime
