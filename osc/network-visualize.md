# Network Auto Visualization by Dash/Cytoscape

<img src="https://dash.plotly.com/assets/images/logo-plotly.png" , style="width:100px;"/>
<img src="https://cytoscape.org/images/logo/cy3logoOrange.svg" , style="width:100px;"/>

- 2021/03/06(Sat)
  - Open Source Conference 2021 Online/Spring

---

## 自己紹介

<img src="https://avatars.githubusercontent.com/u/8357830?s=460&u=b451b623bcc515093cf4ab18acd498df704181f1&v=4", style="width:100px;"/>

- 稲森 景 (Akira Inamori / ainamori@github)
  - 所属
    - IIJ (インフラエンジニア)
  - 主な活動履歴
    - PyConJP
      - 2019 (NOC staff)
      - 2020 (事務局/NOC staff, Speaker)
    - PHP カンファレンス
      - 2019 (NOC staff)
      - 2020 (NOC staff)

---

## 目次

1. 開発背景
1. アプリケーション設計
1. 開発物詳細
1. アプリケーションデモ
1. 今後の展望
1. まとめ

---

## 開発の目的

- インフラの可視化
  - ネットワーク機器の接続状況を瞬時に把握したい
  - ネットワークに参加している機器の情報が知りたい

---

## 開発の動機

- 意外と世の中に存在しない L2 レイヤの可視化ツール

  - L3 以上だとそれなりに存在する
    - でも Netbox は主機能から外れちゃった・・・

- 構築時に設計図って書いてないの？

  - 設計時は<i class="far fa-file-excel"></i>**Excel**で管理されてるのでカンペキ
    - でも現場ではポート不良、急な増設で増えたり減ったりする
  - 設計図で詳細なネットワーク図を書く人はあまりいない

    - L3 以上であれば書くが、以下略

  - そもそも作業が面倒
    - <i class="far fa-file-excel"></i>**Excel**を元に<i class="far fa-file-powerpoint"></i>**PowerPoint**で描く？

---

# ないならば作るしか無い<img src="images/light.png", style="width:150px;"/>

---

## 基本設計

- 入力仕様

  - NW エンジニアが簡単に集められるものにする
    - C 社とか、J 社とか、A 社辺りの汎用的なコマンド・オプションにする
      - show lldp_neighbors (show lldp_neighbors_detail)にした
    - 集めやすく加工しやすい取得方法にする
      - json とか YAML とか
      - ansible gather_fatcs とか
    - [napalm](https://napalm-automation.net/)で解決

- 出力仕様
  - Web ブラウザで閲覧できるようにする
    - Github Page, Gitlab Page でも閲覧できると嬉しい
  - ネットワーク図だけでなく機器情報なども取得できるようにする
    - クリック・マウスオーバーで表示とか

---

## 開発コード

- [Dash + cytoscape](https://github.com/plotly/dash-cytoscape)

  - [ドキュメント](https://dash.plotly.com/cytoscape)
    - Python と言っているが cytoscape.js に強く依存
      - javascript でそのまま作れるならば単なる Web サーバに配置できるが・・・
        - スミマセン、javascript ワカリマセン

- 開発上の Tips
  - 実はマニュアルに記載されたパラメータ以外も埋め込める

---

## アプリケーションデモ

- 以下に公開済み

```bash
 $ git clone https://github.com/ainamori/dash-network-visualiser.git
 $ cd dash-network-visualiser
 $ docker-compose up -d
```

---

## 今後の展望

- napalm データの直接取り込み
  - json dumper が別プログラムなのは面倒くさい
- show int, show xxx 連携
  - node/edge 情報以外も埋め込めるならば色々 t 追加する
- Netbox 連携
  - DCIM 連携している方が楽
    - 全部を自分で作るのは荷が重い
    - さりとて何故か世の中の DCIM は描画機能を追加してくれない
- レイヤ機能
  - 理想と現実をレイヤ描画して「ここ違う」とか言えるとよい
- BPG neighbors 等、多用途への拡大

---

## 最後に

- まだまだ開発中なので触ってみてくれる人、要望を上げてくれる方募集
- 一緒に開発したり使ってみたりする人募集
  - PyConJP の配線管理に使えたら面白いかも
  - スタッフ参加はこちら

![QRcode](images/QR_604121.png)

---

## 謝辞/資料一覧

- 本スライドの作成にはこちら(fork copy)を使わせて頂きました

  - https://github.com/yamap55/SlideWithGitHubPages

- 本スライド URL

  - https://ainamori.github.io/SlideWithGitHubPages/?slide=osc/network-visualize.md

- 成果物 repo（再掲
  - https://github.com/ainamori/dash-network-visualiser
