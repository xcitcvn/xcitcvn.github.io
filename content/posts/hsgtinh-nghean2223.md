---
title: "HSG 12 Tỉnh Nghệ An 2022 - 2023"
date: 2022-11-15T15:02:00+07:00
math: true
mathjax: true
tags: ["Đề Thi Tỉnh", "Lớp 12", "Nghệ An", "2022-2023", "Trung Bình"]
---

| Tên bài           | File nguồn      | File Input       | File output      | Thời gian | Bộ nhớ |
| ----------------- | --------------- | ---------------- | ---------------- | --------- | ------ |
| Số không hoàn hảo | KhongHoanHao.\* | KhongHoanHao.Inp | KhongHoanHao.Out | 1 giây    | 1024mb |
| Ổ cắm điện        | ODien.\*        | ODien.Inp        | ODien.Out        | 1 giây    | 1024mb |
| Dãy số đẹp        | Daysodep.\*     | Daysodep.Inp     | Daysodep.Out     | 2 giây    | 1024mb |
| Khởi nghiệp       | KhoiNghiep.\*   | KhoiNghiep.Inp   | KhoiNghiep.Out   | 1 giây    | 1024mb |

Phần mở rộng .\* được thay thế bằng Pas, Cpp, Py ứng với các ngôn ngữ lập trình Pascal, C++, Python.

## Hãy lập trình giải các bài toán sau đây:

### Câu 1. _(6 điểm)_ Số không hoàn hảo

Đức đang làm các bài tập về số học. Đức rất thích số hoàn hảo, đó là các số nguyên dương _n_ mà tổng các ước dương (khác _n_) của _n_ có giá trị bằng 𝑛. Ví dụ, _n_ = 6 là số hoàn hảo, vì 6 có các ước khác 6 là 1, 2, 3; tổng 1 + 2 + 3 = 6. Tuy nhiên, bài tập mà thầy giáo ra cho Đức là số không hoàn hảo. Một số nguyên dương _n_ được gọi là số không hoàn hảo nếu tổng các ước dương (khác _n_) của _n_ có giá trị lớn hơn _n_. Ví dụ, _n_ = 12 là số không hoàn hảo vì 12 có các ước khác 12 là 1, 2, 3, 4, 6; tổng 1 + 2 + 3 + 4 + 6 = 16 lớn hơn _n_ = 12.

#### Yêu cầu:

Cho hai số nguyên dương _a_ và _b_ (2 ≤ a ≤ b ≤ $10^5$). Tính xem có bao nhiêu số không hoàn hảo thuộc đoạn [*a, b*], tức là tính xem có bao nhiêu số nguyên dương _n_ thỏa mãn: _a ≤ n ≤ b_ và _n_ là một số không hoàn hảo.

#### Dữ liệu

Được cho trong tệp văn bản _**KhongHoanHao.Inp**_ gồm hai số nguyên dương _a_ và _b_ được ghi trên 1 dòng và cách nhau bởi dấu cách

#### Kết quả:

Ghi ra tệp văn bản **_KhongHoanHao.Out_** gồm một số nguyên duy nhất là số các số không hoàn hảo thuộc đoạn [*a*, *b*]

#### Ví dụ:

**Test 1:**

```input 1
2 20
```

```output 1
3
```

**Giải thích:** Có 3 số không hoàn hảo thuộc đoạn [2, 20] là: 12, 18, 20.

- Số 12, có các ước khác 12: 1, 2, 3, 4, 6; tổng: 1 + 2 + 3 + 4 + 6 = 16 lớn hơn 12.
- Số 18, có các ước khác 18: 1, 2, 3, 6, 9; tổng: 1 + 2 + 3 + 6 + 9 = 21 lớn hơn 18.
- Số 20, có các ước khác 20: 1, 2, 4, 5, 10; tổng: 1 + 2 + 4 + 5 + 10 = 22 lớn hơn 20.

#### Giới hạn:

- Có 90% số test tương ứng với 90% số điểm thỏa mãn: 2 ≤ a ≤ b ≤ 1000;
- Có 10% còn lại tương ứng với 10% điểm thỏa mãn: 1000 ≤ a ≤ b ≤ 10^5.

### Bài 2: _(5 điểm)_ Ổ cắm điện

Đức cùng nhóm bạn của mình được thầy giáo giao nhiệm vụ hỗ trợ chuẩn bị phòng máy cho kì thi lập trình danh giá được tổ chức sắp tới. Phòng máy có _m_ máy tính, công việc của nhóm Đức là sử dụng các ổ cắm điện có dây để cung cấp nguồn điện cho _m_ máy tính. Phòng máy chỉ có một ổ điện có một khe cắm ở trên tường là đang có điện, và được gọi là ổ điện nguồn. Hiện tại trong nhà kho có _n_ ổ cắm điện có dây, mỗi ổ điện có một số khe cắm và một đường dây nối có phích cắm để có thể cắm đến ổ điện khác. Ta gọi các ổ điện này là ổ điện rời. Một ổ điện rời có điện chỉ khi phích cắm của nó được cắm vào ổ điện nguồn hoặc cắm vào một khe của ổ điện rời đang có điện. Chú ý là chỉ có một ổ điện rời được cắm vào ổ điện nguồn và mỗi khe có nhiều nhất một phích cắm được cắm vào.

![Ổ cắm điện có 2 khe cắm](https://raw.githubusercontent.com/xcitcvn/xclib/main/resources/_gen/images/ocamdien.png)

Để cung cấp nguồn điện cho _m_ máy tính, mỗi máy tính cần được cắm vào một khe của ổ điện rời đang có điện. Cho biết số khe cắm của ổ điện rời thứ _i_ là Ai (1 ≤ Ai ≤ 10; i = 1, 2, 3, … , _n_). Nhóm của Đức muốn sử dụng số ổ điện rời với số lượng ít nhất nhưng vẫn có thể cung cấp nguồn điện cho _m_ máy tính.

#### Yêu cầu:

Tính xem, số lượng ổ điện rời ít nhất cần dùng là bao nhiêu?

#### Dữ liệu:

Cho trong tệp văn bản **_ODien.Inp_** gồm:

- Dòng 1: ghi 2 số nguyên dương _n_ và _m_ tương ứng là số ổ điện rời và số máy tính.
- Dòng 2 ghi 𝑛 số nguyên dương $A_1$, $A_2$,..., An (1 ≤ Ai ≤ 10) lần lượt là số khe cắm của _n_ ổ điện rời.

#### Kết quả:

ghi ra tệp văn bản **_ODien.Out_** gồm một số nguyên duy nhất là số ổ điện rời ít nhất cần sử dụng để cung cấp nguồn điện cho _m_ máy tính. Nếu không thể cung cấp nguồn điện cho _m_ máy tính khi sử dụng cả _n_ ổ điện rời thì ghi ra −1.

#### Ví dụ:

**Test 1:**

```input 1
3 4
3 2 2
```

```output 1
2
```

**Test 2:**

```input 2
5 5
1 3 1 2 1
```

```output 2
-1
```

**Giải thích:**

- Ví dụ 1: Có 3 ổ điện rời và 4 máy tính. Có thể chọn 2 ổ điện là ổ điện 1 và 2:
  - Ổ điện 1 cắm vào ổ điện nguồn.
  - Ổ điện 2 cắm vào 1 khe cắm của ổ điện 1. Như vậy cả 2 ổ điện đều có điện. Ổ điện 1 còn 2 khe cắm chưa sử dụng, ổ điện 2 còn 2 khe cắm chưa sử dụng. Tổng số khe cắm có điện chưa sử dụng là 4. Sử dụng 4 khe cắm này để cung cấp điện cho 4 máy tính bằng cách mỗi máy tính được cắm vào 1 khe.
- Ví dụ 2: Có 5 ổ điện rời và 5 máy tính. Không thể sử dụng 5 ổ
  điện rời để cung cấp điện cho 5 máy tính.

#### Giới hạn:

- Có 50% số test ứng với 50% số điểm thỏa mãn 1 ≤ _n, m_ ≤ 100; 𝑎1 = 𝑎2 = ⋯ = n > 2 = 2.
- Có 50% số test ứng với 50% số điểm thỏa mãn 100 < _n, m_ ≤ 1000

#### [Tải đề bài và Test][link-de-bai]

[link-de-bai]: https://drive.google.com/drive/folders/1sjDpbFwtXTBt8e1wjuIapqDGLonG-_hA?usp=sharing
