
Awesome-mode Generator プラグイン
===

Awesome-modeとは、Photoshopが最近対応した[Generator][1]というプラグイン仕組みの実験的なプラグインです。機能は現在で３つ：音声コマンド認識、音声フィードバック、そしてLeap Motionを使った空中描き。

Generatorの基本紹介は[こちら][2]。

#### デモ:

[![プラグインのデモ・ビデオ](http://andyhall.github.io/generator-awesome/images/generator-demo.png)](https://www.youtube.com/watch?v=_B9gF-iRhiU)

#### Notes:
* 本プラグインは応用的ではありません！Generatorを使えば色んなことを出来るよ、と伝えるためのデモです。
* 現在では少数の環境でしかテストしていません。（Windows上はまだ未確認）　IssueやPull requestは歓迎です。

## インストール方法

 1. 必要であれば [npm][3] をインストールします。
 2. [generator-core][4] のレポジトリをダウンロードまたはクローンします。
 3. ターミナルで`generator-core`フォルダに移動して、`npm install`を実行します。
 4. [本レポジトリ][5]をダウンロードまたはクローンして、当フォルダ内から`npm install`を実行します。
 5. 音声ライブラリ[Julius][6]をインストールします。[Macports][7]を利用すれば`sudo port install julius`ですが、ソースからビルド、バイナリからでもインストールできるようです。 
> Mac上でJuliusのインストールがうまく行かなかったら、portaudioをインストールする直るらしいです。`sudo port install portaudio`を実行してから再度試してください。

## プラグインの起動方法

1. Photoshopを起動して新規ファイルを開きます。
2. ターミナルで`node path/to/generator-core –f path/to/awesome.generate`を実行します。（`path/to/`を、上記のフォルダへのパスを入れ替えます。）  
> "Connection refused"のようなエラーが表示されたら、Photoshopの **環境設定 > プラグイン** でGeneratorとRemote connectionsを有効に設定し、パスワードを'password'を設定してください。
3. プラグインの起動が終わったら、メニューから**ファイル > Generate > Awesome mode**を選択します。
4. Juliusのインストール済みであれば、音声コマンドはもう使えます。Leap MotionデバイスがPCに繋いでれば、認識されます。

### 音声コマンド

音声コマンドを使うには、コマンド前に`おい フォトショ`と言います。コマンドの後に`サンキュ`を言うと次のコマンドも認識されます。つまり、`おいフォトショ... [command]... サンキュ... [command]... `のように使えます。

対応されるコマンド：

* レイヤー [新規 / コピー / 削除]
* ランダム カラー
* 雲
* ボイス モード

### ボイスモード

有効にしますと、音声コマンドに対してフォトショップが声で答えます。有効の切り替えは、音声コマンドの`おいフォトショ.. ボイスモード`でできます。

### Leap Motion

[Leap Motion][8]デバイスをパソコンに繋ぐと自動的に認識されます。指一本をデバイスの前上に指すと、指の位置が画面にマークされます。デバイスの後上に指しますと描けます。現状では描くことがやや重いですので、パフォーマンスのより良い描き方は検討中です。


  [1]: https://github.com/adobe-photoshop/generator-core
  [2]: http://aphall.com/?p=625
  [3]: https://npmjs.org/
  [4]: https://github.com/adobe-photoshop/generator-core
  [5]: https://github.com/andyhall/generator-awesome
  [6]: http://julius.sourceforge.jp/
  [7]: http://www.macports.org/
  [8]: http://www.leapmotion.com