# Network Auto Visualization by Dash/Cytoscape

Author: Akira Inamori <<akira.inamori@tf-ebina.com>>

2021/03/06(Sat) @ Open Source Conference 2021 Online/Spring

---

# 自己紹介

![myphoto](https://avatars.githubusercontent.com/u/8357830?s=460&u=b451b623bcc515093cf4ab18acd498df704181f1&v=4)

- 稲森 景 (Akira Inamori / ainamori@github)
  - 所属
    - IIJ (インフラエンジニア)
  - アカウントなど
  - 主な活動履歴
    - PyConJP
      - 2019, 2020 (NOC staff)
    - PHP カンファレンス
      - 2019, 2020 (NOC staff)

---

# 目次

1. 開発背景
1. アプリケーション設計
1. 開発物詳細
1. アプリケーションデモ
1. 今後の展望
1. まとめ

---

# 開発背景

- ネットワーク機器を設置、運用する上で物理構成が知りたい

  - 設計当時は`Excel`で管理されてるのでカンペキ
    - でも現場ではポート不良、急な増設で増えたり減ったり
  - 実機から情報を取れば良い
    - そこから再び`Excel`に書く？？？
      - そもそも`Excel`は作業指示書であって構成把握には不向き

- 意外と世の中に無い L1, L2 描画ツール

---

# アプリケーション設計

- Input
  - NW エンジニアが簡単に集められる書式を受け付ける
- Output
  - 絵を描く
  - 絵だけでなく、情報も欲しい

---

# 開発物詳細

- Input
  - [napalm](https://napalm-automation.net/)を使って取得するデータを利用する
    - 流石に show lldp 生データは汎用性がなさ過ぎてツライ
- Output
  - (Dash + cytoscape](https://dash.plotly.com/cytoscape]で作った
    - javascript ならばただの Web サーバに配置できる
      - スミマセン、javascript ワカリマセン

---

# アプリケーションデモ

```bash
 $ git clone https://github.com/ainamori/dash-network-visualiser.git
 $ cd dash-network-visualiser
 $ docker-compose up -d
```

- 開発上の Tips
  - 実はマニュアルに記載されたパラメータ以外も埋め込める

---

# 今後の展望

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

# まとめ

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
- 成果物 repo
  - https://github.com/ainamori/dash-network-visualiser
