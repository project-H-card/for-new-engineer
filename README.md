# 株式会社Highstoでのエンジニアが最初に読むもの
株式会社Highsto（以下「ハイスト」）でのエンジニア向けの解説資料をまとめる。

# 心得
- とりあえず書いてみる、動かしてみる！
- インプットは最小限でアウトプット重視！
- わからなかったらとりあえず聞く & 調べる（ChatGPTを含む）

# フロントエンドの最初
## Chrome
ブラウザはChromeを圧倒的に推奨するので、可能ならChromeで今後作業してほしい！

## 1. [ChatGPT](https://chatgpt.com/) 【1分】
ずっと使うから開いて適当に何か聞いてみよう！

ログイン不要で使える！
慣れたらアカウント作ったりアプリを入れてもいいと思う！

## 2. VSCodeのインストールと日本語化 【5分】
[Windows](https://qiita.com/YurimyMiyu/items/5ce7821f1e3e5905c3ee)

ついでに[Live Server](https://webdesign-trends.net/entry/14461)を入れておくと今後めちゃ便利


## 3. まずはフロントエンドの基本を理解してみよう 【2〜4時間】
- 分かる部分はガンガン飛ばして大丈夫！
- 以下の動画を、見ながら実際に書いてみよう！
- __覚えようとしないこと__
  - どうせ1回見るだけじゃ覚えられないので、やりながら覚えたり復習でもう一回見るイメージ
- 時間をかけずに倍速などでざっと見て、分からなかったらやる時に調べればOK


- [HTMLの基本](https://youtube.com/playlist?list=PLwM1-TnN_NN457PTxsvNXxVxN8fkbYHKU&si=BIub90Ha7I5g8fm2)
- [CSSの基本](https://www.youtube.com/watch?v=xBLIzweHYic&list=PLwM1-TnN_NN5jWN09yjtxWng2XZa88ate)
  - 最初は #1〜#3 だけでOK！
- [JSの基本](https://www.youtube.com/watch?v=E08jeQBa1D0)


## 4. 作ってみよう！ 【1〜3時間】
この後はChatGPTをガンガン活用しながら実際に作ってみよう！
以下のお題から面白そうなものを1つでいいから選んでやってみよう！

ChatGPTには、
> 〇〇をHTML, CSS, JS で作りたい。
などという言葉を伝えるだけでそれなりのものが出てくる。仕様などを細かく伝えたらそれも反映してくれる。

参考にしたいサイトのURLを与えたらそれを読み取って再現してくれたりもするはず（ログインなしでどこまでできるかわからない）

これを有効活用しながら作ってほしい！
__ただし、AIに書いてもらったコードは一部を変更した時の動作の変化などを確かめてちゃんと理解するように努め、分からなければChatGPTに聞いたりGoogleで調べたりすること__

### まるばつゲーム
ユーザー同士の対戦でもCPUとの対戦でもいいが、3×3マスのまるばつゲームを作ってみる

#### 理解してほしいこと
- ユーザーのクリックを受け取って反映させるには？
- ゲームエリアをきれいに真ん中に寄せて整列するには？
- ゲームデータと表示はどう関連している？

### ブログ風ページ
好きなブログや [ハイストのお知らせページ](https://highsto.net/news) などをなるべく再現
（別ページへの遷移やヘッダーなどはいらない）

#### 理解してほしいこと
- 要素を横に並べるには？
- 適切な間隔を空けるには？
- 見出しや画像をうまくはめ込むには？
- 画面サイズに合わせて表示を変えるには？

### メモ帳アプリ
メモの一覧を配列で管理し、それを画面に表示する。新規作成と削除ができればOK

### 理解してほしいこと
- データを更新してから画面を更新するという流れ
- フォームやinput、ボタンを使ってデータと画面を連携する


## 5. git, github の理解と設定 【2〜4時間】
[Windows](https://prog-8.com/docs/git-env-win)

- 4番の「GitHubにSSHの設定をする」と6番の「パスワードの確認を省略しよう」はやらなくて大丈夫！
- その代わり、 `git remote add origin <URL>` の `SSH` は `HTTPS` でやるように

これを使って、4で作ったものを自分のGitHubリポジトリにあげてみよう！

[Gitの説明](https://zenn.dev/tmasuyama1114/articles/git-basic-commands) を読んだりして、以下のコマンドの大まかな意味を理解してほしい
- `git init`
- `git add .`
- `git status`
- `git commit -m "コメント"`
- `git push`

（12/17追記 [Git, GitHub　開発の流れと最低限のコマンド集　〜初めてチーム開発に参加する君へ〜](https://qiita.com/zuisho-1848/items/8f407a6a178d80242d41)という記事を書いたのでこれを見て開発の流れを理解して！）


## 6. Fetch, API, JSON の理解 【2〜4時間】
サーバと実際に通信するようなwebアプリを作るにはこのあたりの理解が必須になる

- [この講座がおすすめ](https://www.youtube.com/watch?v=QugDLcOo_EE&list=PLwM1-TnN_NN7-zdRV8YsGUB82VVhfYiWW&index=8)
  - この #8〜#9 を見て実際のコードを書いてみよう！
- JSONでデータをやりとりするのが基本になるので、軽〜く理解してもらうといいと思う
  - [この動画](https://www.youtube.com/watch?v=9LNM5NIJbDQ)とかがいいかも
- 非同期処理・async/awaitについては [僕が書いた記事](https://qiita.com/zuisho-1848/items/a33813b78a008083387b) を読んでもらうと一気に理解が深まると思う

## 7. Node.js のインストール 【10〜20分】
バックエンド（サーバー側）をJavaScriptで書くため、及びフロントエンドでも、ライブラリの管理などの関係で使うJSの実行環境。

[Windows](https://qiita.com/echolimitless/items/83f8658cf855de04b9ce)


## 8. React(Next.js)の理解 【2〜4時間】
ハイストでは、React(Next.js) を使うので、これを実際に書いて理解してもらいたい！

[この動画](https://www.youtube.com/watch?v=nRCNL9T3J98) を見ながら一緒に書いてみよう！

## 9. MySQLの導入 【10〜20分】
[windows](https://prog-8.com/docs/mysql-env-win)

MySQL（DBシステム）はフロントエンドの人は触らないんだけど、ダミーデータなどを用意しないと動かないので、環境だけは作ってほしい！


# バックエンド
※ 以下は、バックエンドをやることになった人のみ

※ Node.js はフロントエンドの7番でインストールしている前提

※ MySQL はフロントエンドの9番でインストールしている前提

## 1. express の理解 【1〜2時間】
この動画を見ながら一緒にコードを書いて、`Express` というNode.jsのサーバーサイドフレームワークを学ぼう
[【Express入門】Node.jsでWebアプリケーションの作り方を１から学ぼう！](https://www.youtube.com/watch?v=Zk7tpzaKv0U)

## 2. MySQL の理解【1〜2時間】
MySQLは長い動画が多かった中、この動画はシンプルに最低限を教えてくれてるので、これを見て基礎を学ぼう！
[SQL基礎講座　15分で理解する！【プログラミング】](https://www.youtube.com/watch?v=37EH-aC1qqE)

サンプルのSQLを [sampleSQL.md](https://github.com/project-H-card/for-new-engineer/blob/main/sampleSQL.md) にまとめたので、一つ一つ実行して理解してみよう！


# モバイルアプリ
※ 以下はモバイルアプリをやることになった人のみ

※ VSCode はフロントエンドの2番でインストールしている前提

## Flutter の環境構築
入れるものは
- `Flutter` そのもの
  - モバイルアプリなどを含むクロスプラットフォーム（色んなもの向けのシステムを同じコードで実装できる）のフレームワーク。
  - 言語としては `Dart` を使う（あまり他で使うことのない言語）
- `Android Studio`
  - エディタでもあるが、どちらかというとAndroidの「エミュレータ」（PCの中でAndroidのスマホを動かせるやつ）を入れるために使う

[Flutter を VSCode で環境構築してみた！＜Windows編＞](https://qiita.com/shimizu-m1127/items/d8dfc2179bc01baaef6b)

↑この記事はだいぶわかりやすい！（8番の「Visual Studio のダウンロード」はしなくて大丈夫）

動画で見たい人は [Mac](https://www.youtube.com/watch?v=kpvVENfDCRc&list=PLuLRJz1UnJzE4-HlkLTG8ARbZ2TDBNHzZ) [Windows](https://www.youtube.com/watch?v=6J-KK1Ft9NY&list=PLuLRJz1UnJzE4-HlkLTG8ARbZ2TDBNHzZ&index=2) がわかりやすい。

## Flutter の理解
[「Flutter大学」の基礎の再生リスト](https://www.youtube.com/playlist?list=PLuLRJz1UnJzEDjRr1XkqyOzFzUi3Df4B0)

この動画を見て理解を深めながら、可能なら一緒に動くものを作ってみてほしい

## ハイストアプリの開発に参加
ハイストアプリは Node.js, MySQL のサーバーを立てていないと起動しないので、この2つのインストールを終わらせてから開発に入ってもらう


# 以下、色々まとめ（最初は見なくていい）
## よく使うツール
- [ChatGPT](https:/chatgpt.com)
  - 万能なテキスト系生成AI。コードを書く、コードの内容の解説、エラー解決、設計や要件定義、リファクタリング、技術選定...などなんでもやってくれる。実際コードの大半はChatGPTで書けるし、言語選定や進め方の相談もするくらい。
- VSCode
  - テキストエディタ。ここでプログラムを書く。今最も熱いエディタで、軽い上に拡張機能でどんどんいろんな機能を追加できる
- Git, GitHub
  - バージョン管理 & バックアップツール。個人のコードもここで管理するし、チームでの開発の場合に真価を発揮する。複数人が同時に編集をしてもなるべく衝突を避けてマージできるし、issue（TODO）の管理なども含めてここでやっていくことが多い。外部のライブラリを使う時も公式情報として見にいく。
- [Google](https://google.com), [Qiita](https:/qiita.com), [MDN](https://developer.mozilla.org/ja/docs/Web)
  - わからないことや知りたいことがあった時はChatGPT以外だと、基本的にGoogleで検索する。その時、日本語で良い記事が出てきやすいのがQiita。web技術に関しては、MDNが一番一般的な公式（っぽい）ドキュメントなので、これもよく使う

## ハイストでよく使う技術
- HTML/CSS/JavaScript(JS)
  - フロントエンド（ブラウザ側）の基本。ユーザーの見た目やブラウザ側の処理を行う基本セット。ここからweb開発の全てが始まる
- TypeScript(TS)
  - JSに型情報定義を強制するもの。大規模開発でエラーを起きづらくできるので基本的にJSを直で書くのではなくこれを使う
- React, Next.js
  - フロントエンドのライブラリ、フレームワーク。JSの中にHTMLを書くJSX記法と、状態を更新すると変えるべきところだけ変えてくれる仮想DOMが特徴。画面遷移が高速になったりいいことたくさん
- Node.js
  - バックエンド（サーバー側）をJavaScriptで書くことが多いので、Node.jsというJSの実行環境を使う。フロントエンドでも、ライブラリの管理などの関係で使うのが基本
- SQL(MySQL)
  - データベースを扱う言語
- Express
  - バックエンドのフレームワーク
- Flutter/dart
  - 主にアプリ開発で使う。クロスプラットフォーム(webやアプリなどを全て同じコードで開発できる)の開発がめちゃ早くできる


## わかりやすい動画
- [JSの基本](https://youtube.com/playlist?list=PLwM1-TnN_NN7-zdRV8YsGUB82VVhfYiWW&si=XrXrzmGLXQFS0W9K)
