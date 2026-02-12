# OAM to COCO Y0 Automator (Lite)

This is a simplified clone of the original app with only 4 pages:

1. `Input Data`
2. `Ranked Data`
3. `COCO Y0 Estimation`
4. `Result`

Removed from this lite version:
- Excluded OAM
- Estimation 2
- History/Database storage

## Flow

1. Upload OAM CSV from the sidebar.
2. Review parsed objects/attributes/input sheet in `Input Data`.
3. Rank data in `Ranked Data` and run COCO Y0.
4. Review COCO Y0 tables/metrics in `COCO Y0 Estimation`.
5. Generate final object ranking in `Result`.

## CSV Requirements

Required row labels in column 0:
- `Direction ID`
- `Attribute ID`
- `Attribute`

Rules:
- `Direction ID = 0`: higher value is better.
- `Direction ID = 1`: lower value is better.

## Tech Stack

- Python
- Streamlit
- Pandas / NumPy
- Requests + BeautifulSoup4
- OpenPyXL
- Matplotlib (optional, PNG export)

## Project Structure

```text
COCO_OAM_Automation_Lite/
  app.py
  README.md
  requirements.txt
  src/
    coco_client.py
    coco_parse.py
    oam_io.py
    ranking.py
    ui_display.py
```

## Run

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
streamlit run app.py
```

## COCO Dependency

This app submits to:
- `https://miau.my-x.hu/myx-free/coco/beker_y0.php`

Internet access is required for COCO runs.
