# HoloLens ハンズオン

（このドキュメントについて、Pull Request 大歓迎です）

## スケジュール

HoloLens 初めての人向けのハンズオンです。   

#|時間|やること|詳細
----|----|----|----
0|前日までに|事前準備|<a href="#prep">こちらの開発環境構築(準備)</a>を完了させておいてください
1|30分間|セミナー (座学)|HoloLens 概要<ol><li>Windows Mixed Reality (MR) とは</li><li>HoloLens 用アプリ開発の流れ</li></ol>
2|15分間|HandsOn (1)|初めての HoloLens チュートリアル。<br />各種操作方法についてレクチャー<br />
3|15分間|HandsOn 手順説明(デモ)|講師(私)がデモをお見せします<br /><ol><li>今日のハンズオンで作るアプリの完成形をお見せする</li><li>Unity Hello 3D World 的なアプリ作成</li><li>MR ToolKit の使い方</li><li>Visual Studio での Coding</li><li>空間認識の機能追加</li></ol>
4|90 - 120分間|HandsOn (2)|（ハンズオン資料へのリンク。随時更新）<ol><li>資料は当日お配りします</li></ol>
5|おまけ|お勧めアプリ紹介|よくMR体験会で使われているアプリ紹介



<a id="prep"></a>
# HoloLens ハンズオン - 開発環境の準備編 -

## 開発 PC と HoloLens の事前準備について

このハンズオンを受講頂くにあたり、準備していただきたい環境の一覧を載せます。
当日は開発 PC と HoloLens を持参してください。

(インストール済みアプリのバージョン確認手順や、具体的なインストール手順は、表の下に記入しています)

#|種類|項目|バージョン|ダウンロード先|当日までのアクション
----|----|----|----|----|----
1<br>![](img/icon/win10.png)|開発機の OS|Windows 10|Fall Creators Update (10/16 公開) 適用済 (つまり `16299.15` 以上)|Windows 設定アプリの「更新とセキュリティ」から|開発 PC にインストール
2<br>![](img/icon/win10.png)|HoloLens の OS|Windows Holographic 10|最新のバージョン|`Settings`  > `Update & Security` > `Device Update` > `Check for updates`<br>`開発者モード` に設定します(方法は後述)|HoloLens にインストール
3<br>![](img/icon/vs2017.png)|開発環境|Visual Studio 2017|`15.4.4`|[visualstudio.com/ja/downloads/](https://www.visualstudio.com/ja/downloads/)|開発 PC にインストール
4<br>![](img/icon/unity.png)|開発環境|Unity|`2017.1.2`|[unity3d.com/.../archive](https://unity3d.com/get-unity/download/archive) の「Unity 2017.1.2」のインストーラで<br>`Windows Store` 用コンポーネント 2 つをチェック入れた状態でインストール|開発 PC にインストール
5|SDK|Windows 10 SDK|`10.0.15063` と `10.0.14393` の両方|Visual Studio のインストーラの「編集」から|開発 PC にインストール
6|SDK|MixedRealityToolkit-Unity for Unity|`v1.2017.1.2`|[github.com/Microsoft/.../Unitypackages](https://github.com/Microsoft/MixedRealityToolkit-Unity/tree/master/External/Unitypackages) の「HoloToolkit-Unity-v1.2017.1.2.unitypackage」|開発 PC にダウンロード
7<br>![](img/icon/holoremoting.png)|HoloLens 用アプリ|Holographic Remoting|最新版| **開発 PC ではなく、HoloLens にインストールしてください。** HoloLens の Windows Store から「[Holographic Remoting](https://www.microsoft.com/ja-jp/store/p/holographic-remoting-player/9nblggh4sv40)」で検索してインストール| **HoloLens に** インストール

## 詳細

## 1. 開発 PC の OS

Windows 10 Fall Creators Update (ビルド番号 `16299`) に統一します。一応 Windows 10 Creators Update (ビルド番号 `15063`) も対応しています。

項目|値
----|----
Windows 10<br>バージョンの確認方法|こちらを参照:「[Windows のバージョン確認方法](https://www.microsoft.com/ja-jp/safety/protect/ver_win.aspx)」の「ビルド番号」
使用するバージョン|Fall Creators Update (10/16 公開) が適用されている (つまり`16299.15` 以上)<br>要は Windows 10 の最新の状態にしておけば間違いないです。(not Insider Preview 版)
アップデートの手順|こちらを参照：「[Windows Update の利用手順 - Windows 10 の場合](https://www.microsoft.com/ja-jp/safety/protect/musteps_win10.aspx)」

![](https://fud.community.services.support.microsoft.com/Fud/FileDownloadHandler.ashx?fid=05415d7b-0480-4f8d-be0f-eeb055c558cd)

また、追加の操作として、`開発者モード` を有効にします。

`設定` > `更新とセキュリティ` > `開発者向け` > `開発者モード`

![](img/devmode.PNG)

## 2. HoloLens の OS

HoloLens の OS のバージョンを最新版に更新します。

まずスタートメニューを出します。     
スタートメニューを出すには `Bloom(ブルーム)` (開花) というジェスチャーをします。下の動画のように、手のひらをぶわっとやってください。

![](https://az835927.vo.msecnd.net/sites/mixed-reality/Resources/images/Bloom-giphy.gif)

すると、スタートメニューが出てきます。

![](img/StartMenu.png)

ここの [ `Settings` ] に視点を合わせ、クリック。( `Air tap` という動作をします)

![](img/Readyandpress.jpg)

すると設定ウィンドウが上がってくるので、次は [ `Update & Security` ] をクリック。

![](img/StartMenu2.png)

`Device Update` > `Check for updates` ( > `Restart now (今すぐ再起動)`)


![](img/settings.jpg)

この作業を `Your device is up to date` (最新) となるまで繰り返します。

### HoloLens を開発者モードに

開発 PC と同様に、HoloLens も開発者モードにします。
   
`Settings` > `Update & Security` > `For Developers` > `Developer mode` を ON にする

こちらの記事が詳しいです：    
[HoloLens チュートリアルの実機動作 by @Suna ](https://qiita.com/Suna/items/194989d8fa1d9bc3cc97)     
↓その記事の画像から        
![](img/holoDevMode.png)     


## 3. 開発 PC にインストールする Visual Studio のバージョン

Visual Studio 2017 をインストールします。インストール済みの場合は最新版に更新します。

項目|値
----|----
Visual Studio 2017<br>バージョンの確認方法|Visual Studio 2017 を起動 > メニューバーの `ヘルプ` (一番右) > `Microsoft Visual Studio のバージョン情報` で出てきたウィンドウの、2 行目に書いてあります (例：`Version 15.4.4`)
必要なバージョン|`15.4.4`
インストール方法|こちらからダウンロード：[https://www.visualstudio.com/ja/downloads/](https://www.visualstudio.com/ja/downloads/)

## 5. Windows SDK をインストール

4 番目の Unity よりも先にこちらを実行してください。

HoloLens のアプリは Windows 10 アプリ(正確に言うと`UWP アプリ`)です。開発にあたり、対応したバージョンの SDK が必要となります。

まず、Visual Studio 2017 のインストーラから「編集」を選びます。

そして **必ず** 以下の SDK にチェックを入れてから「変更」をクリックしてください。
- `10.0.15063`
- `10.0.14393`

![VS installer](img/vsinstaller.jpg)

## 4. Unity

3D アプリを開発するために、今回は Unity を使います。

最新のバージョンではなく、`2017.1.2` を準備してください。

ダウンロードはこちらから：    
[unity3d.com/.../archive](https://unity3d.com/get-unity/download/archive) の「Unity 2017.1.2」の「インストーラー」

![](img/unityin.png)

インストール時に、**必ず** 以下のオプションにチェックを入れてからインストールしてください。

* `Windows Store .NET Scripting Backend` 
* `Windows Store IL2CPP Scripting Backend` 

![unity](img/unityinstall.png)

## 
