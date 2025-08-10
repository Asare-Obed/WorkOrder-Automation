# Work Order Automation

This project automates the generation of **individual work orders per worker** from source data, such as Excel or CSV files. It processes input records, groups them by work order ID and worker, and exports separate output documents ready for printing or sharing.

It was designed for use in **forest restoration and quality control** workflows but can be adapted for any industry where individual work order documents are needed.

---

## 📌 Features
- Reads work order data from Excel or CSV.
- Groups tasks by **work order ID** and **worker**.
- Generates individual work order files for each worker.
- Supports custom templates for consistent formatting.
- Automatically fills in worker names, dates, and other dynamic fields.

---

## 🛠 Requirements
- **Python 3.9+**
- Required packages:
  ```bash
  pandas
  openpyxl
  python-docx
  ```
- Source data in CSV or Excel format with required columns:
  - `work_order_id`
  - `worker`
  - Additional relevant fields (e.g., task details, location, dates)

---

## 📂 Project Structure
```
.
├── src/                    # Python scripts
│   ├── main.py              # Main script to run
│   ├── utils.py             # Helper functions
│   └── templates/           # Word templates for output
├── data/
│   ├── input/               # Input work order files
│   └── output/              # Generated work order docs
├── README.md
└── requirements.txt
```

---

## 🚀 Setup & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/work-order-automation.git
   cd work-order-automation
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Place input data**  
   Add your CSV or Excel file into `data/input/`.

4. **Run the script**
   ```bash
   python src/main.py
   ```

5. **Get your outputs**  
   Generated work order documents will be available in `data/output/`.

---

## ⚙️ Configuration
- **Template path**: Change the template file in `src/templates/`.
- **Field mapping**: Update `utils.py` if your column names differ from the defaults.
- **Output format**: By default, output is `.docx`. You can modify the code to export PDFs.

---

## 📋 Example Workflow
1. Input file contains:
   ```
   work_order_id,worker,task,location,date
   WO-001,John Doe,Pitting,Plot A,2025-08-01
   WO-001,John Doe,Planting,Plot A,2025-08-02
   WO-002,Jane Smith,Weeding,Plot B,2025-08-03
   ```
2. Script groups by work order ID and worker.
3. Outputs:
   - `WO-001_John_Doe.docx`
   - `WO-002_Jane_Smith.docx`

---

## 🖼 Workflow Diagram

```mermaid
flowchart LR
    A[📂 Input Data<br>(CSV/Excel)] --> B[⚙️ Automation Script<br>(Python)]
    B --> C[📊 Group by Work Order ID & Worker]
    C --> D[📝 Generate Individual Work Orders<br>(.docx)]
    D --> E[📁 Output Folder]
```

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).
