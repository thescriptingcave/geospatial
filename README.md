# geo_env

A geospatial Python environment for working with raster data, vector data, satellite imagery, and machine learning. Built on top of GeoPandas, Rasterio, PyTorch, and JupyterLab.

---

## Requirements

| Platform | Python | File |
|---|---|---|
| macOS (Apple Silicon / Intel) | 3.11 | `reqtext_p312_mac.txt` |
| Linux x86_64 | 3.12 | `reqtext_p312_linux.txt` |

> **Note:** The two files differ because some packages (`pyobjc`, `appnope`) are macOS-only, and several packages like `rasterio 1.5.0` and `torch 2.12.0` require Python 3.12 which is only used on the Linux side.

---

## Prerequisites

### macOS

1. **Homebrew** — if not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **GDAL** — required by rasterio:
   ```bash
   brew install gdal
   ```

3. **uv** — fast Python package manager:
   ```bash
   brew install uv
   ```

### Linux (Ubuntu / Debian)

1. **GDAL** — required by rasterio:
   ```bash
   sudo apt update
   sudo apt install gdal-bin libgdal-dev python3-dev build-essential
   ```

2. **uv** — fast Python package manager:
   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

---

## Installation

### macOS

```bash
# 1. Clone the repo
git clone https://github.com/thescriptingcave/geospatial.git
cd geospatial

# 2. Create and activate a virtual environment with Python 3.11
uv venv --python 3.12
source .venv/bin/activate

# 3. Install dependencies
uv pip install -r reqtext_p312_mac.txt
```

### Linux

```bash
# 1. Clone the repo
git clone https://github.com/thescriptingcave/geospatial.git
cd geospatial

# 2. Install Python 3.12 if not already available
uv python install 3.12

# 3. Create and activate a virtual environment with Python 3.12
uv venv --python 3.12
source .venv/bin/activate

# 4. Install dependencies
uv pip install -r reqtext_p312_linux.txt
```

---

## Starting JupyterLab

Once your environment is activated:

```bash
jupyter lab
```

This will open JupyterLab in your browser at `http://localhost:8888`.

---

## Key Packages

| Category | Packages |
|---|---|
| Geospatial | GeoPandas, Rasterio, Shapely, PyProj, osmnx, Folium |
| Raster / imagery | Rasterio, imagecodecs, tifffile, imageio, opencv-headless |
| Machine learning | PyTorch, torchvision, scikit-learn, scikit-image |
| Data science | NumPy, SciPy, Pandas, Matplotlib, SymPy |
| Notebooks | JupyterLab, ipywidgets, nbconvert |

---

## Troubleshooting

**`rasterio` fails to import on Linux**
Make sure GDAL is installed at the system level:
```bash
sudo apt install gdal-bin libgdal-dev
```

**`uv` can't find Python 3.12 on Linux**
Let uv download and manage it:
```bash
uv python install 3.12
```

**`pyobjc` errors on Linux**
This package is macOS-only and is not included in `reqtext_p312_linux.txt`. Make sure you're using the correct requirements file for your platform.

**Dependency conflicts**
Always install inside a fresh virtual environment. If you hit conflicts, try:
```bash
deactivate
rm -rf .venv
uv venv --python 3.12   # or 3.11 on macOS
source .venv/bin/activate
uv pip install -r reqtext_p312_linux.txt
```

---

## Project Structure

```
geo_env/
├── reqtext_p312_mac.txt       # macOS dependencies (Python 3.11)
├── reqtext_p312_linux.txt     # Linux x86_64 dependencies (Python 3.12)
├── README.md
└── notebooks/                 # Jupyter notebooks go here
```

---

## License

MIT
