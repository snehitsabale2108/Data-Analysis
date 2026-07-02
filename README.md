# 📊 Data Analyzer

A desktop GUI application built with **Python, Tkinter, Pandas, and Matplotlib** that lets non-technical users analyze CSV/Excel data, build grouped reports, visualize results as charts, and export everything — all without writing a single line of code.


---

## ✨ Overview

**Data Analyzer** is a corporate-ready desktop tool designed for business/non-technical users who need quick, interactive summaries of tabular data. Load any CSV or Excel file, pick a column to group by, choose an aggregation, and instantly get a sortable report table — plus a matching chart — all inside a single native window. Reports and charts can be exported with one click, saved right next to the source file.

---

## 🚀 Features

### 1️⃣ File Selection & Reading
- Browse and select any `.csv` or `.xlsx` / `.xls` file
- Dedicated **Read** button loads the full dataset
- Instantly displays:
  - Total number of rows
  - Total number of columns
  - All column headings

### 2️⃣ Dynamic Column Detection
- Automatically classifies columns into:
  - **Text columns** (object/string dtype) → available for grouping
  - **Numeric columns** (true numeric dtypes *or* numeric-looking text like `"12,000"`) → available as aggregation values
- Handles comma-formatted numbers and coerces invalid values safely to `NaN`

### 3️⃣ Interactive Report Builder
- Dropdown-driven report configuration:
  - **Group By** — any text column
  - **Aggregation** — Sum, Mean, Average, Max, Min, Count, Median
  - **Value Column** — any numeric column
- One-click **Preview Report**:
  - Cleans and title-cases group labels
  - Applies the selected GroupBy + aggregation
  - Sorts results in descending order
  - Renders the result directly inside the GUI (scrollable table, no Excel required)

### 4️⃣ Export Report
- Export the generated report as:
  - **Excel** (`.xlsx`)
  - **CSV** (`.csv`)
- Automatically saved into the **same folder as the input file**

### 5️⃣ Chart Builder (GUI-Based Visualization)
- Choose from **Bar**, **Column**, **Line**, or **Pie** charts
- **Preview Chart** renders the top 10 grouped results directly inside the app using Matplotlib
- **Export Chart** saves a high-resolution PNG (200 DPI) to the input file's folder

### 6️⃣ Usability & Error Handling
- Clear popup messages for missing files, unread data, or empty dropdown selections
- Previous report/chart outputs are refreshed automatically on each new run
- Clean, professional, single-window layout — no coding required by the end user

---

## 🖼️ Application Layout

```
┌───────────────────────────────────────────────────────────┐
│  Data Analyzer                                             │
├───────────────────────────────────────────────────────────┤
│  Select CSV/Excel: [Browse] [Read]     No file selected    │
├───────────────────────────────────────────────────────────┤
│  File Info: rows, columns, column headings                 │
├───────────────────────────────────────────────────────────┤
│  Build Report: [Group By ▾] [Aggregation ▾] [Value ▾]      │
│  [Preview Report]     Export as: [Excel ▾] [Export Report] │
├───────────────────────────────────────────────────────────┤
│  Chart Builder: [Chart Type ▾] [Preview Chart] [Export PNG]│
├───────────────────────────────────────────────────────────┤
│   Report Preview (Table)   │      Chart Preview            │
└───────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Component        | Technology              |
|-------------------|--------------------------|
| GUI Framework      | Tkinter (`ttk` widgets) |
| Data Processing    | Pandas                  |
| Charting           | Matplotlib (`TkAgg` backend) |
| Language           | Python 3.9+              |
| Packaging (optional) | PyInstaller (build to `.exe`) |

---

## 📦 Installation

### Prerequisites
- Python 3.9 or higher

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/data-analyzer.git
cd data-analyzer
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

**`requirements.txt`**
```
pandas
matplotlib
openpyxl
```
> `tkinter` ships with standard Python installations on Windows/macOS. On Linux, install it via `sudo apt install python3-tk`.

### 3. Run the application
```bash
python "Data Analysis.py"
```

---

## 🧭 Usage

1. Click **Browse** and select a `.csv` or `.xlsx` file.
2. Click **Read** — the app displays row/column counts and headings, and populates the dropdowns.
3. Select a **Group By** column, an **Aggregation Method**, and a **Value** column.
4. Click **Preview Report** to generate and view the grouped, sorted table.
5. (Optional) Choose an export format and click **Export Report** to save the report next to your input file.
6. Select a **Chart Type** and click **Preview Chart** to visualize the top 10 results.
7. Click **Export Chart (PNG)** to save the chart image.

---

## 📂 Project Structure

```
data-analyzer/
├── Data Analysis.py     # Main application (GUI + logic)
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

---

## 🏗️ Building a Standalone Executable (Optional)

To distribute the app to users without Python installed:

```bash
pip install pyinstaller
pyinstaller --onefile --windowed "Data Analysis.py"
```

The `.exe` (or platform equivalent) will be generated inside the `dist/` folder.

---

## 🔮 Roadmap / Ideas for Future Enhancements
- Multi-column grouping support
- Filter builder before aggregation
- Dark mode theme
- Save/load report configurations as presets
- Support for `.json` and Google Sheets input

---

## Author

**Snehit Sabale**
[GitHub](https://github.com/snehitsabale2108)

---
