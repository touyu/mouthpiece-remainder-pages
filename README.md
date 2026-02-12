# mouthpiece-remainder-pages

アプリの利用規約・プライバシーポリシー・サポートページをホスティングするためのリポジトリ。

## URL

- プライバシーポリシー: https://touyu.me/mouthpiece-remainder-pages/privacy.html
- 利用規約: https://touyu.me/mouthpiece-remainder-pages/terms.html
- サポート: https://touyu.me/mouthpiece-remainder-pages/support.html

## ホスティング

GitHub Pagesを使用。

- Source: `main` branch / `/docs` folder

## Submodule

このリポジトリは [mouthpiece-remainder](https://github.com/touyu/mouthpiece-remainder) に `pages/` ディレクトリとしてsubmodule追加されている。

### 編集方法

```bash
# mouthpiece-remainder リポジトリ内で
cd pages
# ファイルを編集
git add .
git commit -m "Update pages"
git push

# 親リポジトリに戻ってsubmoduleの参照を更新
cd ..
git add pages
git commit -m "Update pages submodule"
git push
```

### クローン時の注意

親リポジトリをクローンする際はsubmoduleも取得する:

```bash
git clone --recursive https://github.com/touyu/mouthpiece-remainder.git
```

または、クローン後に:

```bash
git submodule update --init
```
