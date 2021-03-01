## Python(Dash/Cytoscape)を使ったNetwork Auto Visualization

 Author: Akira Inamori <<akira.inamori@tf-ebina.com>>

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



### 備考欄
　「やってみた」といえばそのままですが
　dash(cytoscape)のソースコードを参照しながら
　「実はこんな情報も詰め込める」というちょっとしたHack/Tipsを交えて紹介したいと思います。

---

## Slide URL
- http://yamap55.github.io/SlideWithGitHubPages/index.html?slide=example/slide1.md

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