---
title: "Code tham khảo đề thi HSG 9 Hà Nội 2015 - 2016"
date: 2022-11-30T12:03:09+07:00
katex: true
---

**Lưu ý:** _Các code được chia sẻ dưới đây có thể không AC (không full test)_.

### Câu 1: Tích lấy dư:

```cpp
#include <bits/stdc++.h>

using namespace std;

#define taskname "cau1"

void sol() {
    int a, b, c;    cin >> a >> b >> c;
    int res = 1;
    for (int i = a; i <= b; ++i) {
        res = (res * (i % c)) % c;
    }
    cout << res;
}

int main() {
    if (fopen (taskname".inp", "r")) {
        freopen (taskname".inp", "r", stdin);
        freopen (taskname".out", "w", stdout);
    }

    cin.tie (0)->sync_with_stdio (0);
    sol();  return 0;
}
```

### Câu 2: Điểm thưởng:

```cpp
#include <bits/stdc++.h>

using namespace std;

#define taskname "cau2"

void sol() {
    int n;  cin >> n;
    int curr = 0;
    for (int i = 0; i < n; ++i) {
        int x;  cin >> x;
        curr = max(curr, x);
        cout << curr << " ";
    }
}

int main() {
    if (fopen (taskname".inp", "r")) {
        freopen (taskname".inp", "r", stdin);
        freopen (taskname".out", "w", stdout);
    }

    cin.tie (0)->sync_with_stdio (0);
    sol();  return 0;
}
```

### Câu 3: Tìm xâu:

```cpp
#include <bits/stdc++.h>

using namespace std;

#define taskname "cau3"

void sol() {
    int k;  cin >> k;   cin.ignore();
    string s;   cin >> s;
    int n = s.length();
    vector<string> per;
    map<string, bool> f;

    for (int i = 0; i < n; ++i) {
        if (!f[s]) {
            per.push_back(s);
            f[s] = 1;
        }
        s += s[0];  s.erase(0, 1);
    }
    if ((int) per.size() <= k) {
        cout << -1;
    } else {
        sort(per.begin(), per.end());
        cout << per[k-1];
    }
}

int main() {
    if (fopen (taskname".inp", "r")) {
        freopen (taskname".inp", "r", stdin);
        freopen (taskname".out", "w", stdout);
    }

    cin.tie (0)->sync_with_stdio (0);
    sol();  return 0;
}
```

### Câu 4: Di chuyển cây:

```cpp
#include <bits/stdc++.h>

using namespace std;

#define taskname "cau4"

int m, n, T;
int a[111][111];

bool inCol(int R, int C) {
    int t = R,  b = R;
    while (t - 1 && a[t-1][C] == a[R][C]) --t;
    while (b + 1 <= m && a[b+1][C] == a[R][C]) ++b;
    return (b - t + 1 >= T);
}

bool inRow(int R, int C) {
    int l = C,  r = C;
    while (l - 1 && a[R][l-1] == a[R][C]) --l;
    while (r + 1 <= n && a[R][r+1] == a[R][C]) ++r;
    return (r - l + 1 >= T);
}

void sol() {
    cin >> m >> n >> T;
    for (int i = 1; i <= m; ++i) {
        for (int j = 1; j <= n; ++j) {
            cin >> a[i][j];
        }
    }
    int keep = 0;
    for (int i = 1; i <= m; ++i) {
        for (int j = 1; j <= n; ++j) {
            if (a[i][j] == 0 || inRow(i, j) || inCol(i, j)) {
                ++keep;
            }
        }
    }
    cout << n*m - keep;
}

int main() {
    if (fopen (taskname".inp", "r")) {
        freopen (taskname".inp", "r", stdin);
        freopen (taskname".out", "w", stdout);
    }

    cin.tie (0)->sync_with_stdio (0);
    sol();  return 0;
}
```
