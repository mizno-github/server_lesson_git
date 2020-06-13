# サーバレッスン
calectl status
Linuxプラクティス
-----------------
### vagrant系
- brew cask install vagrant vagrantのインストール
- vagrant -v vagrantのバージョン確認
- init	設定ファイルの生成	box名を指定し作成するのが基本
- box add	boxの追加	URLを記述する場合は、ネット上のboxを元に作成する
- box remove	boxの削除	box名をオプションで付与する
- up	起動
- ssh	仮想環境にssh接続を行う
- halt	起動中の仮想環境を停止
- reload	起動中の仮想環境を再起動
- destroy	対象仮想環境の削除　ただしboxは消えない
- status	vagrantの起動状態の確認
- vagrant plugin install	vagrantにプラグインをインストールする
- vagrant plugin list	プラグインのリスト

今回利用したコマンド
- vagrant box add centos/7
- vagrant plugin install vagrant-vbguest
	- vagrant-vbguestは初めに追加したBoxの中にインストールされているGuest Additionsというもののバージョンを、VirtualBoxのバージョンに合わせて最新化してくれるプラグインです
### cent0S/7 で利用したコマンド
- sudo yum -y install パッケージ名
- sudo yum -y groupinstall "導入する名称"
	- yum パッケージ管理ツール・コマンド  Macの brew 
	- 例えば、-y オプションを付けずに大量のパッケージをインストールしようとした場合、個々のパッケージのインストールごとに yes/no の入力を求められてスクリプトが停止してしまい面倒であるため、忘れずに付けるようにしましょう。
- sudo yum -y groupinstall "development tools"
- phpのインストール
	- sudo yum -y install epel-release wget
	- sudo wget http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
	- sudo rpm -Uvh remi-release-7.rpm
	- sudo yum -y install --enablerepo=remi-php71 php php-pdo php-mysqlnd php-mbstring php-xml php-fpm php-common php-devel php-mysql unzip
	- php -v
- composerのインストール
	- php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
	- php composer-setup.php
	- php -r "unlink('composer-setup.php');" 


### ファイル操作
 - cd	移動
	- ~	ホームディレクトリ
	- /	ルートディレクトリ
	- -	移動前に位置していたディレクトリ
	- . 	ワーキングディレクトリ
	- ..	ワーキングディレクトリの一階層上のディレクトリ
	- ../../	ワーキングディレクトリの二階層上のディレクトリ
- mkdir	ディレクトリの作成
- touch ファイルの作成
- ls	自分が現在位置しているディレクトリ内に存在するディレクトリやファイルを一覧表示
	- -a	不可視ファイルも表示
	- -l	タイプや権限、所有者や所有グループなどの詳細情報を表示
- pwd	ワーキングディレクトリ がどこであるか出力
- &&	左辺の実行が成功すれば、右辺を実行する
- cp コピー前. php コピー後.php 複製
	- -r	ディレクトリの複製	
- mv	ファイル名やディレクトリ名を変更する、またファイルやディレクトリの移動を行う
	- 移動させるかは指定先に既に存在するか否か操作対象がファイルかディレクトリかによって変わる
	- mv text.php file1	この場合は移動（拡張子は変えられないため？）
        - mv file1 file2	この場合は移動も名前変更も可能性あり、見分けかたは右辺のファイル名が存在しているか。（存在していれば移動）
- rm	ファイルの削除　-r をつければディレクトリも削除できる
- ワイルドカード(*,?)
	- *部分一致、文字数は特に関係なし
        - ?文字数関係あり
- echo 文字列　>.php　左辺の実行結果出力を右辺で指定したファイルに上書きする
- echo 文字列　>> 左辺の実行結果出力を右辺で指定したファイルに追加する
- cat　ファイルの中身を出力する

### vi系
vi ファイル名　起動

モード切り替え操作
- i	インサートモードに切り替え
- escキー	ノーマルモードに切り替え

ノーマルモード時操作
- j	下に移動
- k	上に移動
- h	左に移動
- l	右に移動
- :w	保存
- :wq	保存して終了
- :q!	保存せずに強制終了
- u	変更内容を一つもとに戻す
- Ctrl + r	変更内容を一つ前にすめる
