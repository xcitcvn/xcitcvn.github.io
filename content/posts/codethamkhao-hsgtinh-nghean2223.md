---
title: "Code tham khảo đề thi HSG 12 Tỉnh Nghệ An 2022 - 2023"
date: 2022-11-15T15:02:00+07:00
katex: true
---

**Lưu ý:** _Các code được chia sẻ dưới đây có thể không AC (không full test)_.

### Câu 1: Số không hoàn hảo.

```cpp
#include <bits/stdc++.h>

#define fi "KhongHoanHao.inp"
#define fo "KhongHoanHao.out"

#define ll long long

#define	oFin freopen(fi, "r", stdin);
#define oFot freopen(fo, "w", stdout);

using namespace std;

ll f[1000005];

void setUp(int r) {
    memset(f, 0, sizeof(f));
    for (int i = 2; i <= r; ++i) {
        f[i] += 1;
        for (int j = 2*i; j <= r; j += i) {
            f[j] += i;
        }
    }
}

int main() {
    oFin;	oFot;
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);	cout.tie(NULL);
        int a, b;   cin >> a >> b;
        setUp(b);
        int cnt = 0;
        for (int i = a; i <= b; ++i) {
            if (f[i] > i) ++cnt;
        }
        cout << cnt;
    return 0;
}
```

### Câu 2: ổ cắm điện.

```cpp
#include <bits/stdc++.h>

#define fi "ODien.inp"
#define fo "ODien.out"

#define ll long long

#define	oFin freopen(fi, "r", stdin);
#define oFot freopen(fo, "w", stdout);

using namespace std;

int main() {
    oFin;	oFot;
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);	cout.tie(NULL);
        int n, m;   cin >> n >> m;
        int a[n+5];
        for (int i = 0; i < n; ++i) {
            cin >> a[i];
        }
        sort(a, a+n, greater<int>());
        int i = 0;
        for (int total = 1; total < m; ++i) {
            total += (a[i] - 1);
        }
        cout << ((i > n) ? -1 : i);
    return 0;
}
```

### Câu 3: dãy số đẹp.

```cpp
#include <bits/stdc++.h>

#define fi "Daysodep.inp"
#define fo "Daysodep.out"

#define ll long long

#define	oFin freopen(fi, "r", stdin);
#define oFot freopen(fo, "w", stdout);

using namespace std;

int main() {
    oFin;	oFot;
	ios_base::sync_with_stdio(false);
	cin.tie(NULL);	cout.tie(NULL);
        ll n, k;   cin >> n >> k;
        ll l[n+5],  c[n+5], cnt = 0;
        l[0] = 0;
        c[0] = 0;
        for (int i = 1; i <= n; ++i) {
            int x;  cin >> x;
            if (x % 2 == 1) {
                l[i] = l[i-1] + x;
                c[i] = c[i-1];
            } else {
                c[i] = c[i-1] + x;
                l[i] = l[i-1];
            }
            if (i > 1) {
                for (int j = 1; j < i; ++j) {
                    int x = c[i] - c[j-1],
                        y = l[i] - l[j-1];
                    if (x && y && x - y >= 0 && x - y <= k) {
                        ++cnt;
                    }
                }
            }
        }
        cout << cnt;
    return 0;
}
```

### Câu 4: khởi nghiệp.

```cpp
#include <bits/stdc++.h>

using namespace std;

#define taskname "KhoiNghiep"

#define ii pair<int, int>
#define vii vector<ii>

void sol() {
    long long n, ans = 0;   cin >> n;
    vii comp(n);
    for (ii &x : comp) cin >> x.first >> x.second;
    sort(comp.begin(), comp.end());

    multiset<int> st;
    int j = 0;
    for (int i = 0; i < n; ++i) {
        while (j < n && comp[j].first <= i) st.insert(comp[j++].second);
        if (st.size()) st.erase(--st.end());
    }

    for (int i = j; i < n; ++i) ans += comp[i].second;
    for (auto x : st) ans += x;

    cout << ans;
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
