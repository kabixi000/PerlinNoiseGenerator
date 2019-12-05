# Git Useful Commands
よく使ってるコマンドを集約
#### 困ったときは一旦ここを見る
- [【永久保存版】Gitのあらゆるトラブルが解決する神ノウハウ集を翻訳した - LABOT 機械学習ブログ](https://blog.labot.jp/entry/2019/07/01/183204)
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
#### 直前コミットにリセット
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
#### 403エラーがでてPushできなくなったとき
- `git config --local`の`user.name`や`user.email`が正しく設定されていることを確認
- 上記を正しく設定しても403の場合`git config --local`の`remote.origin.url`を`https://<USERNAME>@github.com/XXXXXX/<RepositoryName>.git`に変えてPush
- それでもだめな場合は`git config --local`の`remote.origin.url`を`https://<USERNAME>:<PASSWORD>@github.com/XXXXXX/<RepositoryName>.git`にしてPush
- Pushできたら`:<PASSWORD>`の部分を削除しておく
- (上記設定は.git/configからも行える)