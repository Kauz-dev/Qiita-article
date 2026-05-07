---
title: 【2回目】AtCoder Beginner Contest 456 に出てみた
tags:
  - Python
  - AtCoder
  - 初心者
  - 競技プログラミング
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---

## はじめに

2026年5月2日、AtCoder Beginner Contest 456 に参加しました。前回（ABC455）に続き2回目の参加です。

今回はA・B問題をAC、C問題に挑戦しましたが解けませんでした。

---

## 結果

![Rating推移](https://raw.githubusercontent.com/Kauz-dev/Qiita-article/main/public/2026-05-02_atcoder-abc456/images/rating.png)

| 項目 | 内容 |
|------|------|
| 参加回数 | 2回目 |

---

## A問題：Dice

- 言語：Python（CPython 3.13.7）
- 提出日時：2026-05-02 21:05:49
- コード長：109 Byte、実行時間 11ms でAC
- 所要時間：約5分

![A問題結果](https://raw.githubusercontent.com/Kauz-dev/Qiita-article/main/public/2026-05-02_atcoder-abc456/images/A_result.png)

前回より格段に早く解けるようになった実感があります。問題を読んで素直に実装するだけで5分でAC。少しずつ慣れてきた感じがします。

---

## B問題：456

**問題概要**

6 つの面を持つサイコロが 3 個あります。
$i$ 個目のサイコロの $j$ 個目の面には $A_{i,j}$ が書かれています。
どのサイコロも、各面が出る確率は $\frac{1}{6}$ です。

これらのサイコロを同時に振ったとき、4・5・6 の書かれた目が 1 つずつ出る確率を求めてください。

**提出情報**

- 言語：Python（CPython 3.13.7）
- 1回目（WA）：2026-05-02 21:29:09
- 2回目（AC）：2026-05-02 21:32:21、1022 Byte、11ms

![B問題結果](https://raw.githubusercontent.com/Kauz-dev/Qiita-article/main/public/2026-05-02_atcoder-abc456/images/B_result.png)

**提出コード**

```python
A = list(map(int, input().split()))
B = list(map(int, input().split()))
C = list(map(int, input().split()))
count_4_A = 0
count_4_B = 0
count_4_C = 0
count_5_A = 0
count_5_B = 0
count_5_C = 0
count_6_A = 0
count_6_B = 0
count_6_C = 0
for i in range(6):
    if A[i] == 4:
        count_4_A += 1 
    if A[i] == 5:
        count_5_A += 1 
    if A[i] == 6:
        count_6_A += 1 
    if B[i] == 4:
        count_4_B += 1 
    if B[i] == 5:
        count_5_B += 1 
    if B[i] == 6:
        count_6_B += 1 
    if C[i] == 4:
        count_4_C += 1 
    if C[i] == 5:
        count_5_C += 1 
    if C[i] == 6:
        count_6_C += 1 
pattern_1 = count_4_A/6*count_5_B/6*count_6_C/6
pattern_2 = count_4_A/6*count_6_B/6*count_5_C/6
pattern_3 = count_5_A/6*count_4_B/6*count_6_C/6
pattern_4 = count_5_A/6*count_6_B/6*count_4_C/6
pattern_5 = count_6_A/6*count_4_B/6*count_5_C/6
pattern_6 = count_6_A/6*count_5_B/6*count_4_C/6
print(pattern_1+pattern_2+pattern_3+pattern_4+pattern_5+pattern_6)
```

各サイコロに 4・5・6 が何面あるかをカウントし、3つのサイコロが 4・5・6 をそれぞれ担当する 6 通りの順列パターンの確率をすべて足し合わせるという方針です。

スマートとは言えませんが、考え方は正しかったので何とかAC。`count_4_A` のような変数名を大量に作るよりも、辞書やリスト内包表記でまとめる方がすっきり書けそうです。

---

## C問題：Not Adjacent

- 言語：Python（CPython 3.13.7）
- 提出日時：2026-05-02 22:11:15、155 Byte、43ms でWA

![C問題結果](https://raw.githubusercontent.com/Kauz-dev/Qiita-article/main/public/2026-05-02_atcoder-abc456/images/C_result.png)

考え方の方向性は掴めた気がしましたが、正解には至りませんでした。コンテスト後に解説を読んで理解を深める予定です。

---

## 振り返り

- **よかった点**：A問題を5分でAC、前回解けなかったB問題もACできた
- **反省点**：B問題のコードが冗長。C問題の考察が足りなかった
- **次の目標**：B問題をよりすっきりしたコードで解く。C問題に手が届くようになる

## 次回に向けて

今回は初めてB問題をACできて、少し自信がつきました。
一方でコードの書き方はまだ改善の余地があるので、同じ問題をより短く書き直す練習もしていこうと思います。

C問題は解説を読んで理解し、次回以降に活かします。
