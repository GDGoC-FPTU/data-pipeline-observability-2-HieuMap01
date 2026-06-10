[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112846&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** minhhieu12092003@gmail.com

**Name:** Bui Minh Hieu

---

## Mo ta

Lab nay xay dung mot ETL pipeline don gian cho du lieu san pham. Pipeline doc du lieu tu `raw_data.json`, validate cac record loi, transform du lieu hop le, va luu ket qua vao `processed_data.csv`. Bai lam cung co phan observability thong qua logging so record duoc xu ly, so record bi loai, va cot `processed_at` trong output.

---

## Cach chay (How to Run)

### Prerequisites

```bash
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Pipeline se tao file:

```bash
processed_data.csv
```

### Chay Agent Simulation (Stress Test)

Tao garbage data:

```bash
python generate_garbage.py
```

Chay agent simulation:

```bash
python agent_simulation.py
```

### Chay test local

```bash
python -m pytest tests
```

---

## Cau truc thu muc

```text
solution.py              # ETL Pipeline script
processed_data.csv       # Output cua pipeline
experiment_report.md     # Bao cao thi nghiem
agent_simulation.py      # Script mo phong AI agent
generate_garbage.py      # Script tao garbage_data.csv
raw_data.json            # Du lieu dau vao
README.md                # File huong dan
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`. Sau validation, co 3 valid records va 2 errors dropped. Hai record bi loai do `price <= 0` va `category` rong. Output `processed_data.csv` co them cot `discounted_price` bang `price * 0.9`, category duoc chuan hoa thanh Title Case, va cot `processed_at` de theo doi thoi diem xu ly.

Stress test cho thay Clean Data giup agent chon Laptop at $1200, trong khi Garbage Data lam agent chon Nuclear Reactor at $999999 do outlier khong hop ly.
