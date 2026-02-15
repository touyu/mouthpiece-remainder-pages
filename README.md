# mouthpiece-remainder-pages

Alignerアプリのランディングページ・利用規約・プライバシーポリシー・サポートページをホスティングするためのリポジトリ。

## URL

- ランディングページ: https://touyu.me/mouthpiece-remainder-pages/
- プライバシーポリシー: https://touyu.me/mouthpiece-remainder-pages/privacy
- 利用規約: https://touyu.me/mouthpiece-remainder-pages/terms
- サポート: https://touyu.me/mouthpiece-remainder-pages/support

## ファイル構成

```
docs/
├── index.html          # LP（単一テンプレート、JS i18nで多言語対応）
├── i18n/
│   ├── en.json         # 英語翻訳
│   └── ja.json         # 日本語翻訳
├── privacy.html        # プライバシーポリシー
├── terms.html          # 利用規約
└── support.html        # サポート
```

## 多言語対応（i18n）

LPは単一HTMLファイル + JSONで多言語対応しています。

- `index.html` 内の `data-i18n` / `data-i18n-html` 属性でテキストを差し替え
- ブラウザの言語設定で自動判定（日本語ブラウザ → `ja.json`、それ以外 → `en.json`）
- ナビの言語セレクターで手動切り替え可能（`localStorage` で記憶）

### 言語の追加方法

1. `docs/i18n/xx.json` を作成（`en.json` をコピーして翻訳）
2. `index.html` 内の `LANGS` 配列にエントリを追加:
   ```js
   var LANGS = [
       { code: 'en', label: 'English' },
       { code: 'ja', label: '日本語' },
       { code: 'xx', label: 'New Language' }  // 追加
   ];
   ```

## ホスティング

GitHub Pagesを使用。

- Source: `main` branch / `/docs` folder

## Submodule

このリポジトリは [minder](https://github.com/touyu/minder) に `public/` ディレクトリとしてsubmodule追加されている。

### 編集方法

```bash
# minder リポジトリ内で
cd public
# ファイルを編集
git add .
git commit -m "Update pages"
git push

# 親リポジトリに戻ってsubmoduleの参照を更新
cd ..
git add public
git commit -m "Update public submodule"
git push
```

### クローン時の注意

親リポジトリをクローンする際はsubmoduleも取得する:

```bash
git clone --recursive https://github.com/touyu/minder.git
```

または、クローン後に:

```bash
git submodule update --init
```
