# 『CodeIgniter徹底入門』に対するノート

## 第1部 CodeIgniterによるWeb開発

### Chapter 1 CodeIgniterとは

#### 1.1 PHPとCodeIgniterフレームワーク

1.1.1 PHP言語の特徴とフレームワークとの親和性

1.1.2 フレームワークを使う利点

作業工数の削減とコストの低減

ビジネスロジックの作り込みに専念可能

グループによる共同作業の促進

不用意なセキュリティホールの回避

#### 1.2 CodeIgniterの特徴

1.2.1 CodeIgniterの10の利点

①少ないメモリとディスクで動く

②高いパフォーマンス

③PHP4/5対応（Webホスティングとの幅広い互換性）

***
【Note】 P.8

CodeIgniter 2.0からはPHP 5.1.6以上が必要となり、PHP4はサポートされなくなりました。
CodeIgniter 3.0からはPHP 5.2.4以上が必要となり、PHP 5.4以上が推奨となりました。
***

④設定ファイルをほとんど触ることなく動く

⑤コマンドラインによる操作を必要としない

⑥コーディング規約を硬く守ることを強要しない

⑦PEARのような大規模で一枚岩な構造のライブラリを必要としない

⑧テンプレート言語の学習が必要ない

⑨シンプルな機能構成

⑩明確で完全なドキュメント（仕様書）

1.2.2 CodeIgniterの設計思想

コンポーネントの低い結合度と高い凝集度

動的なインスタンス化と疎結合

1.2.3 ライセンス

### Chapter 2 開発環境の構築

#### 2.1 CodeIgniterでの開発に必要なソフトウェア

#### 2.2 XAMPP、Eclipse/PDT、Xdebug

2.2.1 XAMPP

2.2.2 Eclipse/PDT

Windows環境

GNU/Linux環境

2.2.3 Xdebug

Windows環境

GNU/Linux環境

#### 2.3 Windowsでの開発環境の構築

2.3.1 XAMPP for Windows のインストール

手順1　インする

手順4　Apacheを設定する

手順5　ApacheとMySQLを起動する

手順6　Apacheの動作を確認する

2.3.2 Eclipse/PDTのインストール

手順1　インストールファイルを入手する

手順2　Eclipse/PDTをインストールする　

2.3.3 CodeIgniterのインストール

手順1　インストールファイルを入手する

手順2　日本語言語パックを入手する

***
【Note】 P.30

CodeIgniter 2.0からは、CodeIgniter本体と日本語言語パックをまとめた「日本語言語パック All in One パッケージ」のみが日本CodeIgniterユーザ会よりリリースされています。
***

手順3　CodeIgniterを設定する

***
【Note】 P.30

CodeIgniter 2.0からフォルダ構成が変更されており、設定ファイルの場所も変更されています。

~~~ 
C:\CodeIgniter\system\application\config\config.php
 ↓
C:\CodeIgniter\application\config\config.php
~~~
***

手順4　Eclipseでプロジェクトを作成する

手順5　EclipseへCodeIgniterのソースファイルをインポートする

手順6　mod_rewriteを設定する

手順7　CodeIgniterの動作を確認する

#### 2.4 GNU/Linuxでの開発環境の構築

2.4.1 XAMPP for Linuxのインストール

手順1　インストールファイルを入手する

手順2　XAMPPをインストールする

手順3　Xdebugのソースファイルを入手する

手順4　Xdebugのコンパイル、インストール処理を行なう

手順5　PHPを設定する

手順6　XAMPP for Linuxを起動する

2.4.2 Eclipse/PDTのインストール

手順1　インストールファイルを入手する

手順2　Pleiadesをインストールする

手順3　JREをインストールする

手順4　Eclipseを起動する

2.4.3 CodeIgniter

#### 2.5 Eclipse/PDTの設定

2.5.1 ファイルの文字エンコードを設定する

2.5.2 PHPデバッグを設定する

### Chapter 3 CodeIgniterの基礎

#### 3.1 はじめてのCodeIgniterプログラミング

3.1.1 テキストエディタでPHPプログラムを作る

3.1.2 CodeIgniterでPHPプログラムを作る

***
【Note】P.53

CodeIgniter 2.0より、applicationフォルダはsystemフォルダと同じ階層に変更されています。

【Note】P.54

CodeIgniter 2.0より、コントローラは、CI_Controllerクラスを継承するように変更されています。

~~~
class Time_message extends Controller {
↓
class Time_message extends CI_Controller {
~~~
***

#### 3.2 “Hello World!”で学ぶCodeIgniter基本

3.2.1 コントローラとは

3.2.2 コントローラで“Hello World!”を作る

3.2.3 ビューを使用する

#### 3.3 CodeIgniterのURL

3.3.1 URIセグメント

3.3.2 index.phpファイルをURLから取り除く

3.3.3 URLサフィックス（接尾辞）の追加

3.3.4 クエリ文字列ベースアプローち

#### 3.4 ディレクトリ構成

***
【Note】P.64

CodeIgniter 2.0からフォルダ構成が以下のように変更されています。

* applicationフォルダはsystemフォルダと同じ階層に移動されました
* cache、logsフォルダはapplicationフォルダ内に移動されました
* applicationフォルダにthird_partyフォルダが新設されました
* plugins、scaffoldingフォルダは機能の廃止に伴い削除されました
* system/librariesフォルダ内にあったコアクラスのファイルは、system/coreフォルダが新設され、そこに移動されました

【Note】P.64

CodeIgniter 3.0からは、application/errorsフォルダはapplication/views/errorsに移動し、またCLI用のエラーテンプレートが追加されました。
***

3.4.1 systemディレクトリ

application（アプリケーション）ディレクトリ

views（ビュー）ディレクトリ

cache（キャッシュ）ディレクトリ

codeigniter（コードイグナイタ）ディレクトリ

database（データベース）ディレクトリ

fonts（フォント）ディレクトリ

language（言語ファイル）ディレクトリ

helpers（ヘルパー）ディレクトリ

libraries（ライブラリ）ディレクトリ

logs（ログ）ディレクトリ

plugins（プラグイン）ディレクトリ

scaffolding（スカフォールディング）ディレクトリ

3.4.2 ユーザガイドディレクトリ

#### 3.5 アプリケーションの公開

3.5.1 公開時のためのエクスポート

手順1　Eclipseからソースファイルをエクスポート

手順2　PHPエラー表示の設定を変更

***
【Note】P.69

PHPエラー表示の設定はENVIRONMENT定数で標準で制御されるようになりました。
参考: http://codeigniter.jp/user_guide_ja/general/environments.html
***

手順3　「config.php」の変更 

***
【Note】P.70

複数環境のサポートにより、開発用と本番用の設定ファイルを別々に作成することができるようになっています。次のdatabase.phpも同様です。
参考: http://codeigniter.jp/user_guide_ja/libraries/config.html#environments
***

手順4　「database.php」の変更

手順5　「.htaccess」の変更

手順6　ソースファイルをサーバに転送

手順7　セキュリティ強化の設定

手順8　パーミッションの設定

***
【Note】P.72

logs、cacheフォルダはapplicationフォルダに移動されました。
***

### Chapter 4 CodeIgniterのMVCモデル

#### 4.1 MVCモデルの特徴

#### 4.2 コントローラ

4.2.1 コントローラとURI

***
【Note】P.79

CodeIgniter 2.0より、コントローラは、CI_Controllerクラスを継承するように変更されています。

~~~
class Sample01 extends Controller {
↓
class Sample01 extends CI_Controller {
~~~
***

4.2.2 コントローラの命名規則

4.2.3 コントローラのメソッド

4.2.4 デフォルトメソッド

ユーザ定義のメソッド

メソッドに引数を渡す

4.2.5 プライベートメソッド

4.2.6 再マップメソッド

4.2.7 コンストラクタメソッド

***
【Note】P.91

コンストラクタメソッドは、PHP5のコンストラクタ__construct()とし、親クラスのコンストラクタはparent::__construct()で呼び出すように変更します。

~~~
class Sample07 extends Controller {

    function Sample07()
    {
        // 
        parent::Contorller();
↓
class Sample07 extends CI_Controller {

    function __construct()
    {
        // 
        parent::__construct();
~~~
***

4.2.8 出力メソッド

4.2.9 予約済みメソッド名

***
【Note】P.94

変更されてます。
参考: http://codeigniter.jp/user_guide_ja/general/reserved_names.html
***

#### 4.3 ビュー

4.3.1 ビューの命名規則

4.3.2 ビューの使い方

4.3.3 マルチビュー

4.3.4 レイアウト機能を持たせたビュー

4.3.5 ループ

#### 4.4 モデル

4.4.1 モデルの命名規則

***
【Note】P.108

モデルはCI_Modelを継承するように変更されました。

~~~
class Model_name extends Model {
↓
class Model_name extends CI_Model {
~~~

コンストラクタもコントローラのコンストラクタと同じく、__construct()、parenet::__construct()とします。
***

4.4.2 モデルの利用準備

モデルの読み込み
モデルの自動読み込み

4.4.3 モデルの使い方

### Chapter 5 CodeIgniterの開発支援機能

#### 5.1 ヘルパー

5.1.1 ヘルパーの利用準備

5.1.2 ヘルパーの使い方

#### 5.2 ライブラリ

5.2.1 ライブラリの利用準備

5.2.2 ライブラリの使い方

#### 5.3 Scaffolding

***
【Note】P.122

Scaffolding機能は廃止されました。
***

5.3.1 Scaffoldingを活用するシーン

#### 5.4 デバッグとログ出力

5.4.1 プロファイラ

プロファイラの使い方

5.4.2 ログ出力

ログ出力の使い方

ログの確認

#### 5.5 セキュリティ

5.5.1 CodeIgniterの内部セキュリティ機能

URIセキュリティ

GET、POST、およびクッキーデータ

***
【Note】P.129

CodeIgniter 2.0以降は、$_GETが標準で使えるようになりました。
***

register_globals

magic_quotes_runtime

5.5.2 安全なWebアプリケーションを構築するための方策

XSSフィルタリング

データのバリデーション（検証）

***
【Note】P.131

バリデーション（検証）クラスは、CodeIgniter 1.7より新しいフォームバリデーション（検証）クラスに変更されています。
参考: http://codeigniter.jp/user_guide_ja/libraries/form_validation.html
***

データベースへデータを追加する前に全データをエスケープする

### Chapter 6 CodeIgniterの機能拡張とその他の機能

#### 6.1 ヘルパーの作成と拡張

6.1.1 ユーザ定義の自作ヘルパーの作成

6.1.2 標準ヘルパーの置き換え

6.1.3 標準ヘルパーの継承

#### 6.2 プラグインの作成

***
【Note】P.139

プラグインは廃止されました。ヘルパーを使いましょう。
***

6.2.1 プラグインの利用準備

#### 6.3 ライブラリの作成と拡張

6.3.1 ライブラリの使い方

6.3.2 ユーザ定義の自作ライブラリの作成

6.3.3 標準ライブラリの置き換え

6.3.4 標準ライブラリの継承

***
【Note】

参考: CI的にCodeIgniter 2.xで、iPhone/Androidなどスマートフォンを判別する方法http://goo.gl/ON4b7
***

6.3.5 独自プリフィックスの設定

#### 6.4 コアシステムクラスの拡張

6.4.1 コアシステムクラスの置き換え

6.4.2 コアシステムクラスの継承

#### 6.5 フックによる拡張

6.5.1 フックの有効化

6.5.2 フックの定義

6.5.3 同一のフックポイントで複数呼び出し

#### 6.6 その他の機能

6.6.1 URIルーティング

独自のルーティングを定義する

6.6.2 エラーの処理

エラーの生成

404エラーの表示

6.6.3 Webページのキャッシュ

キャッシュの仕組み

キャッシュの使い方

6.6.4 リソースの自動読み込み

6.6.5 アプリケーションの管理

「application」ディレクトリのリネーム

「application」ディレクトリの再配置

1つのCodeIgniterで複数のアプリケーションを共存させる

### Chapter 7 コンタクトフォームを作る

***
【Note】

以下のリポジトリでこのアプリをCodeIgniter 3.0.0対応にアップデートしています。
https://github.com/kenjis/codeigniter-tettei-apps
***

#### 7.1 コンタクトフォームの設計

7.1.1 機能を考える

7.1.2 ページ遷移とメソッド名を考える

7.1.3 ビューをデザインする

7.1.4 Formの定義を考える

7.1.5 ディレクトリ構成

#### 7.2 セッション

***
【Note】P.170

CodeIgniter 3.0より、セッションデータはデフォルトでサーバ上のファイルに保存されるように変更されました。クッキーにセッションデータを保存する実装は廃止されました。
***

7.2.1 セッションクラスの使い方

セッションのサンプルプログラム

#### 7.3 コンタクトフォームのコーディング

7.3.1 コントローラファイルを作成する

7.3.2 コントローラのコンストラクタを作成する

7.3.3 入力ページのメソッドを作成する

***
【Note】P.178

CodeIgniter 2.0より、自動CSRF保護機能が追加されています。
参考: http://codeigniter.jp/user_guide_ja/libraries/security.html
***

7.3.4 入力ページのビューを作成する

7.3.5 確認ページのメソッドを作成する

7.3.6 確認ページのビューを作成する

7.3.7 完了ページのメソッドを作成する

7.3.8 メールを送信するメソッドを作成する

***
【Note】P.189

件名の処理の仕様がCodeIgniter 1.7.1から変更されているため、$subjectがこのままだと文字化けします。
参考: http://www.yamanoi.org/blog/2011-07-18/

~~~
$subject = mb_convert_mimeheader($subject, 'ISO-2022-JP');
↓
$subject = mb_convert_encoding($subject, 'ISO-2022-JP', 'UTF-8');
~~~
***

7.3.9 完了ページのビューを作成する

### Chapter 8 モバイル対応簡易掲示板を作る

***
【Note】

以下のリポジトリでこのアプリをCodeIgniter 3.0.0対応にアップデートしています。
https://github.com/kenjis/codeigniter-tettei-apps
***

#### 8.1 モバイル対応簡易掲示板の設計

8.1.1 機能を考える

8.1.2 モバイル対応について検討する

8.1.3 ページ遷移とメソッド名を考える

8.1.4 Formの定義を考える

8.1.5 テーブルの定義を考える

8.1.6 ディレクトリ構成

#### 8.2 データベースの利用

8.2.1 データベースおよびユーザの作成

8.2.2 テーブルの作成

8.2.3 データベース接続設定

8.2.4 データベースクラスの基本的な使い方

8.2.5 データベースクラスの初期化

8.2.6 データベース利用の典型的なパターン

複数行の結果を取得する問い合わせ

***
【Note】

CodeIgniter 3.0からActive RecordはQuery Builderに名称変更されました。
***

結果を調べる

1行の結果を返す問い合わせ

新規レコードの作成

レコードの削除

#### 8.3 ページネーション

#### 8.4 モバイル対応簡易掲示板のコーディング

8.4.1 コントローラファイルを作成する

8.4.2 コントローラのコンストラクタを作成する

***
【Note】P.212

CodeIgniter 2.0からは文字エンコードのチェックがシステムの初期化時に行なわれるため、それ以前に文字エンコードの変換をする必要があります。
参考: http://d.hatena.ne.jp/taramonera/20110720/1311127617
***

_convert_encoding()メソッドを作成する

8.4.3 記事表示ページのメソッドを作成する

8.4.4 記事表示ページのビューを作成する

モバイル版のビューを作成する

8.4.5 新規投稿ページのメソッドを作成する

_set_validation()メソッドを作成する

_show_post_page()メソッドを作成する

captcha_check()メソッドを作成する

8.4.6 新規投稿ページのビューを作成する

8.4.7 投稿確認ページのメソッドを作成する

8.4.8 記事登録処理のメソッドを作成する

8.4.9 削除ページのメソッドを作成する

8.4.10 出力文字エンコードを変換するメソッドを作成する

### Chapter 9 簡易ショッピングサイトを作る

***
【Note】

以下のリポジトリでこのアプリをCodeIgniter 3.0.0対応にアップデートしています。
https://github.com/kenjis/codeigniter-tettei-apps
***

#### 9.1 簡易ショッピングサイトの設計

9.1.1 機能を考える

9.1.2 ページ遷移とメソッド名を考える

9.1.3 ビューをデザインする

9.1.4 テーブルの定義を考える

9.1.5 データベースを設定する

データベースおよびユーザの作成

テーブルの作成

データベース接続設定

9.1.6 ディレクトリ構成

9.1.7 設定ファイルを変更する

検索キーワードをURIセグメントに含める

***
【Note】P.249

CodeIgniter 2.0からは$_GETが標準で使えるため、検索キーワードはGETで渡すように変更した方がよいです。
***

セッションデータの暗号化

#### 9.2 簡易ショッピングサイトのコーディング

9.2.1 コントローラファイルを作成する

9.2.2 設定ファイルを作成する

9.2.3 コントローラのコンストラクタを作成する

9.2.4 モデルファイルを作成する

9.2.5 商品を登録する（Scaffoldingの利用）

***
【Note】P.255

Scaffoldingは廃止されました。ここでは、phpMyAdminなどを利用してください。
***

商品画像の仕様

Scaffoldingとは

Scaffoldingの使い方

9.2.6 カテゴリ別商品一覧ページを作成する

データを取得するメソッドを作成する

カテゴリ別商品一覧ページのメソッドを作成する

カテゴリ別商品一覧ページのビューを作成する

9.2.7 個別商品ページを作成する

商品データを取得するメソッドを作成する

個別商品ページのビューを作成する

9.2.8 ショッピングカートを作成する

***
【Note】P.266

CodeIgniter 1.7.2よりカートクラスが追加されましたので、このカートクラスを使うのもよいでしょう。
参照: http://codeigniter.jp/user_guide_ja/libraries/cart.html
***

カートに商品を追加するメソッドを作成する

個別商品ページの入力を処理するメソッドを作成する

カートの情報を取得するメソッドを作成する

カート内の商品数を取得するメソッドを作成する

カートを表示するメソッドを作成する

カートのビューを作成する

9.2.9 検索結果ページを作成する

商品のキーワード検索をするメソッドを作成する

検索結果を表示するメソッドを作成する

ページネーションを生成するメソッドを作成する

検索結果ページのビューを作成する

9.2.10 お客様情報入力ページを作成する

お客様情報入力ページのビューを作成する

整形／検証ルール設定用メソッドを作成する

入力データを保存するメソッドを作成する

入力データを取得するメソッドを作成する

整形／検証を行なうメソッドを作成する

9.2.11 注文内容確認ページを作成する

入力されたお客様情報を処理するメソッドを作成する

注文内容確認ページのビューを作成する

9.2.12 注文完了ページを作成する

注文完了ページを表示するメソッドを作成する

注文データを処理するメソッドを作成する

メール送信を行なうメソッドを作成する

***
【Note】P.288

件名の処理の仕様がCodeIgniter 1.7.1から変更されているため、$subjectがこのままだと文字化けします。
参考: http://www.yamanoi.org/blog/2011-07-18/

~~~
$subject = mb_convert_mimeheader($subject, $config['charset']);
↓
$subject = mb_convert_encoding($subject, $config['charset'], $this->config->item('charset'));
~~~
***

注文完了ページのビューを作成する

### Chapter 10 CodeIgniterレシピ集

#### 10.1 Ajax for CodeIgniter

10.1.1 Ajax for CodeIgniterのインストール

10.1.2 ポップアップの表示

コントローラの作成

ビューの作成

動作の確認

10.1.3 非同期通信での表示の書き換え

コントローラの作成

ビューの作成

動作の確認

10.1.4 Ajaxフォーム

コントローラの作成

ビューの作成

動作の確認

10.1.5 ソート可能なリスト

コントローラの作成

ビューの作成

動作の確認

10.1.6 テキスト入力フィールドの自動補完

コントローラの作成

ビューの作成

動作の確認

#### 10.2 Yet Another Smarty～Smartyと連携

10.2.1 SamrtyとYet Another Smartyのインストール

Smarty

Yet Another Smarty

10.2.2 Yet Another Smartyの利用

コントローラの作成

ビューの作成

動作の確認

#### 10.3 PEAR::Spreadsheet_Excel_Writer～PEARライブラリと連携

10.3.1 PEAR::Spreadsheet_Excel_Writerのインストール

PEAR

PEAR::Spreadsheet_Excel_Writer

PEAR::OLE

10.3.2 PEAR::Spreadsheet_Excel_Writerの利用

コントローラの作成

動作の確認

#### 10.4 simplelogin～シンプルな認証ライブラリ

***
【Note】

参考: CodeIgniter2.XでSimpleLoginを使う http://1bit.mobi/20110327190631.html
参考: DA AuthをCodeIgniter2.0.xで使う方法 http://goo.gl/HYlqZ
***

10.4.1 simpleloginのインストール

***
【Note】P.324

CodeIgniter WikiはGitHubに移行し、Zipファイルなどのダウンロードはできなくなりましたが、ソースはGitHubのWikiに残っています。
https://github.com/EllisLab/CodeIgniter/wiki/Simplelogin
***

MySQLのテーブルの作成

10.4.2 シンプルな認証ライブラリの利用

コントローラの作成

ビューの作成

simpleloginでの認証

#### 10.5 OpenID

***
【Note】

参考: GREE OAuth認証をCodeIgniter 2.xで構築する方法 http://goo.gl/GYLGv
***

10.5.1 OpenIDの認証フロー

10.5.2 OpenIDライブラリのインストール

ライブラリのダウンロード

***
【Note】P.332

CodeIgniter WikiはGitHubに移行し、Zipファイルなどのダウンロードはできなくなりましたが、ソースはGitHubのWikiに残っています。
https://github.com/EllisLab/CodeIgniter/wiki/OpenID
***

ライブラリのインストール

10.5.3 日本語言語ファイルの作成

10.5.4 OpenIDの利用

コントローラの作成

ビューの作成

OpenIDでの認証

#### 10.6 Amazon Webサービス～Zend Frameworkとの連携

10.6.1 Zend Frameworkのインストール

10.6.2 Zend_Service_Amazonを使うための準備

10.6.3 Zend_Service_Amazonの利用

コントローラの作成

ビューの作成

動作の確認

#### 10.7 Wikipedia API

10.7.1 Wikipedia APIの概要

入力仕様

出力仕様

10.7.2 Wikipedia APIの利用

コントローラの作成

ビューの作成

動作の確認
