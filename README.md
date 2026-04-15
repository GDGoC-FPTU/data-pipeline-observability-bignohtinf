[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574207&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** email@example.com
**Name:** (Dien ten cua ban)

---

## Mo ta

Bai lab nay huong dan xay dung mot ETL pipeline don gian de lam sach va xu ly du lieu san pham, sau do danh gia tac dong cua chat luong du lieu den ket qua cua mot AI agent. Ban se thuc hien tien trinh validate, loai bo du lieu loi va so sanh ket qua agent khi su dung du lieu sach va du lieu rac.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Chay script agent_simulation.py de test voi 2 bo du lieu:
python agent_simulation.py
# Script se tu dong test voi processed_data.csv (du lieu sach) va garbage_data.csv (du lieu rac)
# Ket qua se hien thi tren terminal, so sanh phan hoi cua agent voi tung bo du lieu.
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- Validation summary: 3 kept, 2 dropped
- Errors found: id=3 (Price <= 0), id=4 (Missing Category)
- 3 records duoc luu vao processed_data.csv
- Agent voi du lieu sach: "Based on my data, the best choice is Laptop at $1200."
- Agent voi du lieu rac: "Based on my data, the best choice is Nuclear Reactor at $999999."
