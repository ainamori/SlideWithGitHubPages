## Python(Dash/Cytoscape)を使ったNetwork Auto Visualization

 Author: Akira Inamori <<akira.inamori@tf-ebina.com>>
 2021/03/06(Sat) @ Open Source Conference 2021 Online/Spring


---

## 自己紹介

![myphoto](https://avatars.githubusercontent.com/u/8357830?s=460&u=b451b623bcc515093cf4ab18acd498df704181f1&v=4)

- 稲森 景 (Akira Inamori)
  - ainamori@github
  - インフラエンジニア
  - 主な活動履歴
    - PyConJP 2019, 2020 NOC staff
    - PHPカンファレンス 2019, 2020 NOC staff

---

## 開発背景


- Swith/Routerの接続状況を確認する方法や描画ツールは数多く存在するがL3以上のレイヤで記載する物が殆どであり、物理レイヤに焦点を当てたツールは少ない。
- 概念的な構成把握も重要だが、NOC作業に重要なのは「このデバイスのこのポートは、どのデバイスのどこのポートに繋がって（刺さって）いるのか」です。
- そこで、本発表ではネットワーク機器から得た情報（lldp neighbors)を元に
接続状況を描画する事を試みたのでその成果を発表します。

---

### 関連技術

- napalm: (https://napalm-automation.net/)
- dash/cytoscape: https://dash.plotly.com/cytoscape

---

### 成果物
　https://github.com/ainamori/dash-network-visualiser
　　（docker-composeで起動することで簡単にデモ閲覧が可能）

---

### デモ


#### Code hack

- 実はこんなこともできる
 - node info, edge info以外にも詰め込める


---

## Slide URL
- https://ainamori.github.io/SlideWithGitHubPages/?slide=osc/network-visualize.md

---

## Lists

- List1
- List2
- List3

---

## vertical scroll

- first slide

--

- second slide

---

## code

```python
def main():
    print("Hello World")
```

---

## image1 img1.jpg

![image](img1.jpg)

---

## image2 img/img2.jpg

![image](img/img2.jpg)

---

## image3 absolute path

![image](http://yamap55.github.io/Slide/20170827/img1.jpg)

---

## 謝辞


https://github.com/ainamori/SlideWithGitHubPages