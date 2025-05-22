# Spotify Streams Predictor

Eine Machine-Learning-Pipeline, die basierend auf Spotify- und Apple-Music-Kennzahlen sowie Audio-Features vorhersagt, wie viele Streams ein Track erreichen wird.

## 📥 Datasets

This project relies on two CSVs in `data/`:

1. **Most Streamed Spotify Songs 2024**  
   Download manually from  
   [Most Streamed Spotify Songs 2024](https://www.kaggle.com/datasets/nelgiriyewithana/most-streamed-spotify-songs-2024)

   and save as `data/Most Streamed Spotify Songs 2024.csv`

2. **Spotify Features**  
   Download manually from  
   [Spotify Features](https://www.kaggle.com/datasets/talhazulfiqar426/spotify-features)
   and save as `data/SpotifyFeatures.csv`
---

## 📂 Projektstruktur

```
data/
  Most Streamed Spotify Songs 2024.csv
  SpotifyFeatures.csv
notebooks/
  spotify-streams-predictor.ipynb
.gitignore
README.md
requirements.txt
```

---

## 🚀 Installation

```bash
git clone https://github.com/LionelKoch/spotify-streams-predictor.git
cd spotify-streams-predictor

# (Optional) virtuelles Environment
python3 -m venv venv
source venv/bin/activate

# Abhängigkeiten installieren
pip install -r requirements.txt
```

---

## 🛠 Usage

**Vor dem Start:** Lege die CSV-Dateien in `data/` ab.

1. Öffne das Repository in deiner Entwicklungsumgebung.  
2. Starte deine bevorzugte Notebook-Umgebung (Jupyter, VS Code, Colab …).  
3. Öffne `notebooks/spotify-streams-predictor.ipynb`.  
4. Folge den Kommentaren im Notebook:
   - Daten laden & Vorverarbeitung  
   - Explorative Datenanalyse (EDA)  
   - Hyperparameter-Suche (RandomizedSearchCV)  
   - Finales Modell trainieren & evaluieren  

---

## 📈 Ergebnisse

- **CV R² (Train):** ca. 0.81 ± 0.04  
- **Test R²:** ca. 0.86  
- **Test RMSE:** ca. 1.06  

### Permutation Importances

| Feature                     | ΔR²  |
| --------------------------- | ----:|
| Apple Music Playlist Count  | 0.45 |
| Spotify Popularity          | 0.25 |
| Danceability                | 0.20 |
| Energy                      | 0.12 |
| Tempo                       | 0.08 |
| Valence                     | 0.06 |

---

## 📦 requirements.txt

```text
pandas>=1.5
numpy>=1.23
scikit-learn>=1.1
matplotlib>=3.5
seaborn>=0.12
notebook
jupyterlab  # optional
```

---

## ⚙️ .gitignore

```gitignore
# Jupyter
.ipynb_checkpoints/

# große Datendateien & Exporte
*.csv
*.xlsx

# Cache
.cache/

# lokale Notebook-Backups
*_Copy*.ipynb

# nur diese Dateien versionieren
!notebooks/spotify-streams-predictor.ipynb
!README.md
!requirements.txt
```

---

✍️ **Autor**  
Lionel Koch  
https://github.com/LionelKoch
