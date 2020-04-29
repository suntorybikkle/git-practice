# GitHub練習用

## Git開発 基本の流れ

### issueで作業内容の把握

- issueに対して作業者が割り当てるため、それに対処
- 作業内容については、issue内で検討することになるかもしれない
- 要件が決まったら作業開始

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

- `git checkout -b`で同時に行える
- 移動先のブランチで作業をする

### 変更内容をコミット

```
$ git add 変更したファイル名
$ git commit -m "コメント"
```

- 編集内容の粒度に注意して、適宜コミット
- コメントにはプレフィックスをつけるとみやすい
- コミット時にはissue番号を関連付ける
- ex.) `add: #12 ログインボタンの追加`
- issue閉じるキーワードもあるため注意
- issueに紐づけると以下のようになる (画像ではマージの紐づけもされている)

<image src=https://user-images.githubusercontent.com/60565605/80596018-a94b4f80-8a60-11ea-845d-8cb590a7de02.png width=600>


### リモートにプッシュ

```
$ git push origin hoge-branch
```

### プルリクエストをしてマージ

- ブラウザ上で行う
- `hoge-branch`の内容を`root-branch`に反映依頼する
プルリクエストの作成

<image src=https://user-images.githubusercontent.com/60565605/80591420-a2204380-8a58-11ea-92d9-892a90e28571.png width=700>

作ったブランチを指定してマージリクエストを作成
  
<image src=https://user-images.githubusercontent.com/60565605/80591653-004d2680-8a59-11ea-9b33-bdaf26ff4f0e.png width=300>

本文中に対応内容と、issue番号を書いて紐づける

<image src=https://user-images.githubusercontent.com/60565605/80593888-f3cacd00-8a5c-11ea-9cb0-c456a087fc1d.png width=600>

マージされるまで待つ  
場合によっては、リクエスト中でコメントのやり取りが発生する

### ブランチを移動して不要になったブランチを削除

```
$ git checkout root-branch
$ git branch -d hoge-branch
```

- `git push --delete origin hoge-branch`でリモートを削除

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
- 引数次第でいろいろな箇所の差を見れる

### 変更の一時退避

```
$ git stash save
$ git stach list
$ git stash apply stash@{0}
$ git stash drop stash@{0}
```
