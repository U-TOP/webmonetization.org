# WebMonetization.org

[ウェブサイトを見る](https://webmonetization.org)

このレポジトリはウェブマネタイゼーション標準案のベースになります。

[エクスプレイナー](https://webmonetization.org/docs/explainer.html)を見る, もしくは、 [仕様](https://webmonetization.org/specification.html)を読む。

## コントリビュート

このサイトは、[Docusaurus](https://docusaurus.io/)を使って構築されています。

### ローカル環境での開発

1. ウェブサイトの依存関係が全てインストールされていることを確認してください:

```sh
# Install dependencies
$ cd website
$ yarn
```

2. 開発用サーバーを起動します:

```sh
# Start the site
$ yarn start
```

### ディレクトリのストラクチャ

プロジェクトファイルのストラクチャは下のようにしてください:

```
webmonetization.org
├── docker-compose.yml
├── Dockerfile
├── docs
│   ├── api.md
│   ├── assets
│   │   └── flow.svg
│   ├── explainer.md
│   ├── getting-started.md
│   ├── receiving.md
│   ├── sending.md
│   └── specification.md
├── LICENSE
├── README.md
└── website
    ├── core
    │   └── Footer.js
    ├── i18n
    │   └── en.json
    ├── package.json
    ├── pages
    │   └── en
    │       ├── docs.js
    │       ├── index.js
    │       └── meta-tag.js
    ├── sidebars.json
    ├── siteConfig.js
    ├── static
    │   ├── css
    │   │   └── custom.css
    │   ├── img
    │   │   ├── coil_logo.svg
    │   │   ├── copy_icon.svg
    │   │   ├── favicon.ico
    │   │   ├── fav-webmonetization.png
    │   │   ├── gatehub_logo.svg
    │   │   ├── grey_wm_logo.svg
    │   │   ├── stronghold_logo.svg
    │   │   ├── tipbot_logo.svg
    │   │   ├── webmon_icon_simple.svg
    │   │   ├── webmon_icon.svg
    │   │   ├── wm-icon-animated.svg
    │   │   └── wm-icon.svg
    │   ├── js
    │   │   └── custom.js
    │   └── specification.html
    └── yarn.lock
```

## コンテンツの編集

### 既存のドキュメントページの編集

`docs/`に移動し、対応するドキュメントを編集します:

`docs/doc-to-be-edited.md`

```markdown
---
id: page-needs-edit
title: This Doc Needs To Be Edited
---

Edit me...
```

さらに詳しくは、
[こちら](https://docusaurus.io/docs/en/navigation)

## コンテンツの追加

### 既存のサイドバーに新しいドキュメントを追加する

1. `/docs`に、新しいマークダウンのドキュメントを作成します。例えば
   `docs/newly-created-doc.md`です:

```md
---
id: newly-created-doc
title: This Doc Needs To Be Edited
---

My new content here..
```

1. `website/sidebar.json`の既存のサイドバーでドキュメントIDを参照します:

```javascript
// Add newly-created-doc to the Getting Started category of docs
{
  "docs": {
    "Getting Started": [
      "quick-start",
      "newly-created-doc" // new doc here
    ],
    ...
  },
  ...
}
```

新しいドキュメントの追加に関して、さらに詳しくは
[こちら](https://docusaurus.io/docs/en/navigation)

###サイトのトップナビゲーションバーにアイテムを追加する

1. `website/siteConfig.js`のヘッダーリンクを編集して、ドキュメント、カスタムページおよび外部リンクにリンクを追加します:

`website/siteConfig.js`

```javascript
{
  headerLinks: [
    ...
    /* you can add docs */
    { doc: 'my-examples', label: 'Examples' },
    /* you can add custom pages */
    { page: 'help', label: 'Help' },
    /* you can add external links */
    { href: 'https://github.com/facebook/Docusaurus', label: 'GitHub' },
    ...
  ],
  ...
}
```

ナビゲーションバーに関して、さらに詳しくは
[こちら](https://docusaurus.io/docs/en/navigation)

### カスタムページを追加する

1. DocusaurusはReactコンポーネントを使用してページを構築します。 コンポーネントは次の名前で保存されます
   .js files in `website/pages/en`:
1. ナビゲーションヘッダーにページを表示するには、
   `website/siteConfig.js` をアップデートして `headerLinks` 要素に追加する必要があります:

`website/siteConfig.js`

```javascript
{
  headerLinks: [
    ...
    { page: 'my-new-custom-page', label: 'My New Custom Page' },
    ...
  ],
  ...
}
```

カスタムページに関して詳しくは、
[こちら](https://docusaurus.io/docs/en/custom-pages).

## 完全なドキュメント

完全なドキュメントは [website](https://docusaurus.io/) を参照してください。
