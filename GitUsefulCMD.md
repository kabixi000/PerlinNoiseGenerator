# Git Useful Commands
よく使ってるコマンドを集約
#### 現在のブランチをもとにブランチを作成してチェックアウト
```bash
git checkout -b "BranchName"
```
- 説明通り
- これだけだとローカルブランチしか作られない
#### ブランチをリモートに登録
```bash
git push -u origin 作成したブランチ名
```
- [現在のブランチをもとに新規ブランチ作成](#現在のブランチをもとにブランチを作成してチェックアウト)で作ったブランチをリモートに登録
#### 別ブランチチェックアウト
```bash
git checkout "切り替えるブランチ名"
```
- 説明通り
#### コミットツリー表示
```bash
git log --oneline --decorate --graph --branches --tags --remotes
```
- GUIソフトをいちいち立ち上げたりするのがめんどくさいとき
#### 全ブランチとチェックアウト状態確認
```bash
git branch -a
```
- 説明通り
- #### 直前コミットにリセット
```bash
git reset --hard HEAD^
```
- よく分からない操作をしてもとに戻せなくなったときに使う
- HARDモードでリセットするので変更は消えてしまうので注意
#### ブランチの追跡状態確認
```bash
git branch -vv
```
- たまにローカルブランチとリモートトラッキングブランチの名前がずれるため、その確認
#### Gitツリーをグラフィカル表示
```bash
gitk --all
```
- Git for Windowsをインストールしたときに一緒についてくるやつを使う
- VSCodeの拡張機能を使ったほうがわかりやすいが、これだけでも基本的なGitの操作をGUIで行える
#### 困ったときはここを見る
[【永久保存版】Gitのあらゆるトラブルが解決する神ノウハウ集を翻訳した - LABOT 機械学習ブログ](https://blog.labot.jp/entry/2019/07/01/183204)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE3MTQ4MjE4MywxMTQ2NzA3NjczLC0xOT
g0NzE5OTE2LDExNDY3MDc2NzMsNDEwMDc2NDQsMTQwNDQ2NDM2
NCwtNjU5NTY4MDUyXX0=
-->