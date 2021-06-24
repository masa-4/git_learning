# Gitを操作してみましょう
## 1, リモートリポジトリからローカルにソースコーどをクローンする

```
$ git clone  https://github.com/masa-4/git_learning.git
```

## 2, 自分の作業ブランチを切ってみましょう

```
// branch_nameの部分は自分の名前をアルファベット小文字にしてください
// ex: git branch tajiri
$ git branch branch_name
```

## 3, テキストファイルを編集してください
## 4, 変更差分をステージングしましょう

```
// 変更のあったファイルをすべて表示してくれます
$ git status

// 変更差分を表示してくれます。
$ git diff path/to/file_name

// 変更差分をステージングします 
$ git add path/to/file_name
```
TechAcademyで習った、`git add .`はすべての変更差分をステージングします。
これによりPRに不要な差分までもが入ってしまう可能性が高くなります。
癖として`git status` で変更したファイルを確認してから`git diff`で編集内容が正しいかを確認したのちに`git add`でステージングするようにしましょう。

## 5, コミットしましょう

```
$ git commit -m "message"
```

## 6, 自分の作業ブランチをリモートリポジトリに反映しましょう

```
// originはリモートリポジトリの名前です。
// 試しにgit remote -v を実行してみてください。クローンしたリポジトリのURLが表示されるかと思います。
$ git push origin branch_name
```

---

## 7, PRを出してみましょう
## 8, マージしてみましょう
## 9, マージした内容を取り込んでみましょう

```
// リモートブランチのコピーをローカルに持ってきます
$ git fetch origin main

// リモートブランチの内容とローカルブランチの内容を比較します
$ git diff main origin/main

// 期待差分だったら取り込みましょう
$ git merge origin/main 
```

`git fetch`と`git merge`を同時に行うのが`git pull`です
