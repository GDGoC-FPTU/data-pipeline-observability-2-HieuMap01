# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600876
**Name:** Bui Minh Hieu
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | The clean dataset removed invalid records and normalized categories, so the agent could select a reasonable electronics product. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | The garbage dataset contains an extreme outlier, so the agent selected an unrealistic product as the best answer. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung Garbage Data vi pipeline khong duoc lam sach truoc khi agent doc du lieu. Dataset rac co duplicate IDs, wrong data types, outliers va null values. Trong thi nghiem nay, outlier "Nuclear Reactor" co gia 999999 va category electronics, nen logic cua agent chon no la san pham electronics co gia cao nhat. Neu price co kieu du lieu sai hoac category bi null, agent cung co the bi loi hoac bo qua thong tin quan trong. Dieu nay cho thay chat luong du lieu anh huong truc tiep den ket qua cua AI agent.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot khong the sua hoan toan du lieu dau vao bi sai. Neu data co outlier, duplicate, null value hoac sai kieu du lieu, agent van co the dua ra cau tra loi sai. Lam sach data truoc khi dua vao pipeline giup ket qua dang tin cay hon.
