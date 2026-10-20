# 松陰神社 3D

東京都世田谷区若林の松陰神社の境内を、写真をもとにBlenderで再現した3Dモデルのビューアです。ブラウザでドラッグして回転、ホイールやピンチでズームでき、画面下のボタンで5つの視点(一の鳥居/参道/拝殿/松下村塾/俯瞰)に切り替えられます。

## ファイル構成

```
.
├── index.html        ビューア本体(HTML/CSS/JavaScript を1ファイルに収録)
├── models/
│   └── shoin.glb     3Dモデル(glTF バイナリ, 約9MB)
├── .nojekyll         GitHub Pages で Jekyll 処理を無効にするための空ファイル
└── README.md
```

ビルド作業は不要です。three.js は jsDelivr の CDN から、フォントは Google Fonts から読み込みます。

## 手元で表示する

`index.html` をダブルクリックで開くと、ブラウザの制限でモデルを読み込めません。必ずローカルサーバー経由で開いてください。

```sh
cd shoin-jinja-3d
python3 -m http.server 8000
```

ブラウザで http://localhost:8000 を開きます。

## GitHub Pages で公開する

1. このフォルダの中身をリポジトリのルートに置いて push します。
2. リポジトリの **Settings → Pages** で、**Source** を「Deploy from a branch」、ブランチを `main`、フォルダを `/ (root)` にして保存します。
3. 数分後に `https://<ユーザー名>.github.io/<リポジトリ名>/` で表示されます。

## 操作

| 操作 | マウス | タッチ |
| --- | --- | --- |
| 回転 | 左ドラッグ | 1本指ドラッグ |
| 移動 | 右ドラッグ | 2本指ドラッグ |
| ズーム | ホイール | ピンチ |

URL の末尾に `#gate` `#sando` `#haiden` `#juku` `#aerial` を付けると、その視点から開きます。

## モデルについて

- 鳥居・参道・32基の石灯籠・拝殿・本殿・松下村塾の模築・手水舎を含みます。
- 寸法と配置は写真からの概算で、実測値ではありません。拝殿の幕の神紋は簡略化した図案です。
- 質感は Blender のプロシージャルマテリアルを画像に焼き付けたもので、Web 用にポリゴン数とテクスチャを軽量化しています。

## 使用しているライブラリ

- [three.js](https://threejs.org/) r169(MIT License)
- [Shippori Mincho](https://fonts.google.com/specimen/Shippori+Mincho)、[Zen Kaku Gothic New](https://fonts.google.com/specimen/Zen+Kaku+Gothic+New)(SIL Open Font License)

## ライセンス

未設定です。公開する場合は、リポジトリに `LICENSE` ファイルを追加してください。
