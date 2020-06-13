# サーバレッスン
Linuxプラクティス
-----------------
## vagrant系
brew cask install vagrant vagrantのインストール
vagrant -v vagrantのバージョン確認
init	設定ファイルの生成	box名を指定し作成するのが基本
box add	boxの追加	URLを記述する場合は、ネット上のboxを元に作成する
box remove	boxの削除	box名をオプションで付与する
up	起動
ssh	仮想環境にssh接続を行う
halt	起動中の仮想環境を停止
reload	起動中の仮想環境を再起動
destroy	対象仮想環境の削除　ただしboxは消えない
status	vagrantの起動状態の確認

## vi系
vi ファイル名　起動

モード切り替え操作
i	インサートモードに切り替え
escキー	ノーマルモードに切り替え

ノーマルモード時操作
j	下に移動
k	上に移動
h	左に移動
l	右に移動
:w	保存
:wq	保存して終了
:q!	保存せずに強制終了
u	変更内容を一つもとに戻す
Ctrl + r	変更内容を一つ前にすめる
