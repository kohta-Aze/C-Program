# C++ の環境構築ガイド（Windows）

初めての人でも授業についていけるように、操作を順番に説明します。

**第1回の授業で必ず行うことは、C++ を実行できる環境を用意することです。**

このガイドには動作確認まで載せています。途中で分からなくなったら、授業中に SA または先生に聞いてください。

## このガイドの流れ

| 章 | やること |
| --- | --- |
| 1 | Windows の言語設定を変更する |
| 2 | MinGW をインストールし、動作を確認する |
| 3 | VS Code をインストールする（手順は未掲載） |

> **画像の見方：** 大きなスクリーンショットは表示幅を抑えています。細かい文字を確認したいときは、画像をクリックして元のサイズで開いてください。

---

## 1. Windows の言語設定

### 1-1. コントロール パネルを開く

**Windows キー**を押します。

<a href="image.png"><img src="image.png" alt="Windows キーを押してスタートメニューを開いた画面" width="720"></a>

検索欄に **「コントロールパネル」** と入力します。

<a href="image-1.png"><img src="image-1.png" alt="コントロールパネルを検索した画面" width="720"></a>

検索結果から **「コントロール パネル」** を開きます。

<a href="image-2.png"><img src="image-2.png" alt="検索結果からコントロール パネルを開く" width="720"></a>

### 1-2. 「地域」の設定を開く

**「時計と地域」** を選択します。

<a href="image-3.png"><img src="image-3.png" alt="コントロール パネルの「時計と地域」" width="720"></a>

続いて **「地域」** を選択します。

<a href="image-4.png"><img src="image-4.png" alt="「地域」を選択する画面" width="720"></a>

「地域」の設定画面が開きます。

<a href="image-5.png"><img src="image-5.png" alt="「地域」の設定画面を開いた状態" width="720"></a>

### 1-3. システム ロケールを変更する

**「管理」タブ**を開きます。

<a href="image-6.png"><img src="image-6.png" alt="「地域」の「管理」タブ" width="478"></a>

**「システム ロケールの変更」** を選択します。

<a href="image-7.png"><img src="image-7.png" alt="「システム ロケールの変更」ボタン" width="484"></a>

**「ベータ: ワールドワイド言語サポートで Unicode UTF-8 を使用」** にチェックを入れます。

<a href="image-8.png"><img src="image-8.png" alt="Unicode UTF-8 を使用するチェックボックスをオンにした状態" width="441"></a>

**「OK」** を押して設定画面を閉じます。

**ここまでで、Windows の言語設定は完了です。**

---

## 2. MinGW のインストール

### 2-1. MinGW をダウンロードする

以下のリンクから、元の手順で使用している Windows 向けのファイルをダウンロードします。

**[MinGW をダウンロード（7z ファイル）](https://github.com/niXman/mingw-builds-binaries/releases/download/15.2.0-rt_v13-rev0/x86_64-15.2.0-release-win32-seh-ucrt-rt_v13-rev0.7z)**

保存先を選ぶ画面が出たら、**「保存」** を押します。

<a href="image-9.png"><img src="image-9.png" alt="MinGW のダウンロードファイルを保存する画面" width="640"></a>

### 2-2. ダウンロードフォルダーを開く

**Windows キー**を押し、**「エクスプローラー」** と入力します。

<a href="image-10.png"><img src="image-10.png" alt="エクスプローラーを検索した画面" width="480"></a>

検索結果から **「エクスプローラー」** を開きます。

<a href="image-11.png"><img src="image-11.png" alt="エクスプローラーを開いた画面" width="640"></a>

**「ダウンロード」フォルダー**を開きます。画面の並びや表示場所は、パソコンによって異なる場合があります。

<a href="image-12.png"><img src="image-12.png" alt="エクスプローラーでダウンロードフォルダーを開く" width="640"></a>

ファイル名が **「x86_64」から始まる 7z ファイル**を探します。

<a href="image-13.png"><img src="image-13.png" alt="ダウンロードした圧縮ファイルのアイコン" width="77"></a>

### 2-3. ダウンロードしたファイルを展開する

ファイルを右クリックし、**「すべて展開」** を選択します。

次の画面で **「展開」** を押します。

<a href="image-14.png"><img src="image-14.png" alt="圧縮ファイルの展開先を選び「展開」を押す画面" width="612"></a>

展開が終わるまで待ちます。

<a href="image-15.png"><img src="image-15.png" alt="ファイルの展開中に表示される進行状況" width="607"></a>

展開後のフォルダーが開きます。

<a href="image-16.png"><img src="image-16.png" alt="展開後のフォルダー内にある mingw64 フォルダー" width="640"></a>

### 2-4. 「mingw64」フォルダーを切り取る

**「mingw64」フォルダー**を選択し、**「切り取り」（ハサミのマーク）** を押します。

<a href="image-17.png"><img src="image-17.png" alt="mingw64 フォルダーを選択して切り取る画面" width="640"></a>

次の手順で、移動先の **`C:\tools`** を用意します。

### 2-5. C ドライブに「tools」フォルダーを作る

エクスプローラーで**新しいタブ**を開きます。

<a href="image-18.png"><img src="image-18.png" alt="エクスプローラーで新しいタブを開く操作" width="640"></a>

新しいタブが開いたことを確認します。

<a href="image-19.png"><img src="image-19.png" alt="エクスプローラーの新しいタブを開いた状態" width="640"></a>

左側の一覧を下にスクロールし、**C ドライブ**を探します。

**操作動画：C ドライブを探す**

<video controls preload="metadata" width="720" src="Screen Recording 2026-09-28 100708.mp4" title="C ドライブを探す操作"></video>

[動画を開く：C ドライブを探す](<Screen Recording 2026-09-28 100708.mp4>)

C ドライブを開きます。

<a href="image-20.png"><img src="image-20.png" alt="C ドライブを開いた画面" width="640"></a>

左上の **「新規作成」→「フォルダー」** を選び、名前を **`tools`** にします。

<a href="image-21.png"><img src="image-21.png" alt="新規作成メニューからフォルダーを作る" width="146"></a>

**「tools」フォルダー**が作成されたことを確認します。

<a href="image-22.png"><img src="image-22.png" alt="C ドライブ直下に作成した tools フォルダー" width="640"></a>

### 2-6. 「mingw64」フォルダーを移動する

**「tools」フォルダー**をダブルクリックして開きます。作ったばかりなので、中は空です。

<a href="image-23.png"><img src="image-23.png" alt="作成した tools フォルダーを開いた画面" width="640"></a>

ここに、手順 **2-4** で切り取った **「mingw64」フォルダー**を貼り付けます。

**操作動画：フォルダーを移動する**

<video controls preload="metadata" width="720" src="Screen Recording 2026-09-28 101108.mp4" title="tools フォルダーへ移動する操作"></video>

[動画を開く：フォルダーを移動する](<Screen Recording 2026-09-28 101108.mp4>)

**配置先の確認：** `C:\tools\mingw64` になっていれば、次へ進みます。

不安な場合は、ここで SA に確認してもらってください。

### 2-7. PATH を設定する

以下の動画を見ながら、**PATH** を設定します。

**操作動画：PATH の設定**

<video controls preload="metadata" width="720" src="Screen Recording 2026-09-28 101957.mp4" title="PATH を設定する操作"></video>

[動画を開く：PATH の設定](<Screen Recording 2026-09-28 101957.mp4>)

操作が分からない場合は、SA または先生に聞いてください。

### 2-8. コマンドプロンプトで動作を確認する

**Windows キー**を押し、半角で **`cmd`** と入力します。

**「コマンド プロンプト」** を開き、次のコマンドを入力して **Enter キー**を押します。

```bat
g++ -v
```

次のように、バージョンなどの情報が表示されます。

<a href="image-24.png"><img src="image-24.png" alt="コマンドプロンプトで g++ -v を実行した表示例" width="720"></a>

**確認するのは、出力の最後にある「gcc version」で始まる行です。**

```text
gcc version 15.2.0 ...
```

<a href="image-25.png"><img src="image-25.png" alt="gcc version 15.2.0 と表示された行の拡大画像" width="680"></a>

> 画像は表示例です。バージョン番号や後ろに続く説明は、環境によって異なります。

**バージョン情報が表示されれば、動作確認は完了です。**

---

## 3. VS Code のインストール（手順は未掲載）

このファイルには、VS Code の具体的なインストール手順はまだ掲載されていません。授業中に SA または先生に確認してください。
