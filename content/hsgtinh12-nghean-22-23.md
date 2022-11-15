---
title: "Hsgtinh12 Nghean 22 23"
date: 2022-11-15T15:02:00+07:00
draft: true
---

| Tên bài           | File nguồn      | File Input       | File output      | Thời gian | Bộ nhớ |
| ----------------- | --------------- | ---------------- | ---------------- | --------- | ------ |
| Số không hoàn hảo | KhongHoanHao.\* | KhongHoanHao.Inp | KhongHoanHao.Out | 1 giây    | 1024mb |
| Ổ cắm điện        | ODien.\*        | ODien.Inp        | ODien.Out        | 1 giây    | 1024mb |
| Dãy số đẹp        | Daysodep.\*     | Daysodep.Inp     | Daysodep.Out     | 2 giây    | 1024mb |
| Khỏi nghiệp       | KhoiNghiep.\*   | KhoiNghiep.Inp   | KhoiNghiep.Out   | 1 giây    | 1024mb |

Phần mở rộng .\* được thay thế bằng Pas, Cpp, Py ứng với các ngôn ngữ lập trình Pascal, C++, Python.

## Hãy lập trình giải các bài toán sau

### Câu 1. _(6 điểm)_ Số không hoàn hảo

Đức đang làm các bài tập về số học. Đức rất thích số hoàn hảo, đó là các số nguyên dương _n_ mà tổng các ước dương (khác _n_) của _n_ có giá trị bằng 𝑛. Ví dụ, _n_ = 6 là số hoàn hảo, vì 6 có các ước khác 6 là 1, 2, 3; tổng 1 + 2 + 3 = 6. Tuy nhiên, bài tập mà thầy giáo ra cho Đức là số không hoàn hảo. Một số nguyên dương _n_ được gọi là số không hoàn hảo nếu tổng các ước dương (khác _n_) của _n_ có giá trị lớn hơn _n_. Ví dụ, _n_ = 12 là số không hoàn hảo vì 12 có các ước khác 12 là 1, 2, 3, 4, 6; tổng 1 + 2 + 3 + 4 + 6 = 16 lớn hơn _n_ = 12.

###### Yêu cầu:

Cho hai số nguyên dương _a_ và _b_ (2 ≤ a ≤ b ≤ 10^5). Tính xem có bao nhiêu số không hoàn hảo thuộc đoạn [*a, b*], tức là tính xem có bao nhiêu số nguyên dương _n_ thỏa mãn: _a ≤ n ≤ b_ và _n_ là một số không hoàn hảo.

###### Yêu cầu:

Được cho trong tệp văn bản _**KhongHoanHao.Inp**_ gồm hai số nguyên dương _a_ và _b_ được ghi trên 1 dòng và cách nhau bởi dấu cách

###### Kết quả:

Ghi ra tệp văn bản **_KhongHoanHao.Out_** gồm một số nguyên duy nhất là số các số không hoàn hảo thuộc đoạn [*a*, *b*]

###### Ví dụ:

| KhongHoanHao.Inp | KhongHoanHao.Out |
| ---------------- | ---------------- |
| 2 20             | 3                |

**Giải thích:** Có 3 số không hoàn hảo thuộc đoạn [2, 20] là: 12, 18, 20.

- Số 12, có các ước khác 12: 1, 2, 3, 4, 6; tổng: 1 + 2 + 3 + 4 + 6 = 16 lớn hơn 12.
- Số 18, có các ước khác 18: 1, 2, 3, 6, 9; tổng: 1 + 2 + 3 + 6 + 9 = 21 lớn hơn 18.
- Số 20, có các ước khác 20: 1, 2, 4, 5, 10; tổng: 1 + 2 + 4 + 5 + 10 = 22 lớn hơn 20.

###### Giới hạn:

- Có 90% số test tương ứng với 90% số điểm thỏa mãn: 2 ≤ a ≤ b ≤ 1000;
- Có 10% còn lại tương ứng với 10% điểm thỏa mãn: 1000 ≤ a ≤ b ≤ 10^5.
