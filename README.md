# mouthpiece-remainder-pages

Minderアプリの利用規約・プライバシーポリシー・サポートページをホスティングするためのリポジトリ。

## URL

- プライバシーポリシー: https://touyu.me/mouthpiece-remainder-pages/docs/privacy.html
- 利用規約: https://touyu.me/mouthpiece-remainder-pages/docs/terms.html
- サポート: https://touyu.me/mouthpiece-remainder-pages/docs/support.html

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
