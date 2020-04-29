# GitHub練習用

## Git基本の流れ

### ローカルのリポジトリを最新の状態にする

```
$ git pull origin root-branch
```

- ここでは多くの場合`develop`ブランチ

### 新しいブランチを切って、ブランチを移動

```
$ git branch hoge-branch
$ git checkout hoge-branch
```

- 移動先のブランチで作業をする
- `git checkout -b`で同時に行える

### 変更内容をコミット

```
$ git add 変更したファイル名
$ git comm -m "コメント"
```

- 編集内容の粒度に注意して、適宜コミット
- コメントにはプレフィックスをつけるとみやすい
  - ex.) `add: ログインボタンの追加`

### リモートにプッシュ

```
$ git push origin hoge-branch
```

### プルリクエストをしてマージ

- ブラウザ上で行う
- `hoge-branch`の内容を`root-branch`に反映依頼する

### ブランチを移動して不要になったブランチを削除

```
$ git checkout root-branch
$ git branch -d hoge-branch
```

- リモートの`hoge-branch`はプルリクエスト時に、マージ後削除申請できる

## 便利コマンド

### ブランチ一覧、現在のブランチの確認

```
$ git branch
```

### 現在のブランチの編集状態の確認

```
$ git status
```

### 編集の差分確認

```
$ git diff
```

- 上はステージングの変更の差
- 引数次第でいろいろな個所の差を見れる

### 変更の一時退避

```
$ git stash save
$ git stach list
$ git stash apply stash@{0}
$ git stash drop stash@{0}
```
