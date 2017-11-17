# HoloLens ハンズオン - 開発環境の準備編 -

（このドキュメントについて、Pull Request 大歓迎です）

## 開発 PC や HoloLens にインストールしておくもの一覧表

このハンズオンをやるにあたり、準備していただきたい環境の一覧を載せます。    
(現在の入れてあるアプリのバージョンの確認手順や、具体的なインストール手順などは、表の下に書きます。)

IDs|種類|項目|バージョン|ダウンロード先|当日までのアクション
----|----|----|----|----|----
1<br>![](img/icon/win10.png)|開発機の OS|Windows 10|10/16 に降ってきた Fall Creators Update 以上が適用されている (つまり `16299.15` 以上)|Windows 設定アプリの「更新とセキュリティ」から|開発PCに要インストール
2<br>![](img/icon/win10.png)|HoloLens の OS|Windows Holographic 10|最新のバージョン|`Settings`  > `Update & Security` > `Device Update` > `Check for updates`<br>また、開発者モードに設定もする(方法は後述)|HoloLens に要インストール
3<br>![](img/icon/vs2017.png)|開発環境|Visual Studio 2017|`15.4.x`|[visualstudio.com/ja/downloads/](https://www.visualstudio.com/ja/downloads/)|開発PCに要インストール
4<br>![](img/icon/unity.png)|開発環境|Unity|【決め打ち】<br>`2017.1.2`|[unity3d.com/.../archive](https://unity3d.com/get-unity/download/archive) の「Unity 2017.1.2」のインストーラで<br>`Windows Store` 用コンポーネント2つをチェック入れた状態でインストール|開発PCに要インストール
5|SDK|Windows 10 SDK|【決め打ち】<br>`10.0.15063` と `10.0.14393` |Visual Studio のインストーラの「編集」から|開発PC(VS)に要インストール
6|SDK|MixedRealityToolkit-Unity for Unity|【決め打ち】<br>`v1.2017.1.2`|[github.com/Microsoft/.../Unitypackages](https://github.com/Microsoft/MixedRealityToolkit-Unity/tree/master/External/Unitypackages) の「HoloToolkit-Unity-v1.2017.1.2.unitypackage」|開発PCにダウンロードしておく
7<br>![](img/icon/holoremoting.png)|HoloLens 用アプリ|Holographic Remoting|(何でもいい)| **開発PCではなく、HoloLens に入れます。** HoloLens の Windows Store から「[Holographic Remoting](https://www.microsoft.com/ja-jp/store/p/holographic-remoting-player/9nblggh4sv40)」で検索してインストール| **HoloLens に** 要インストール

## 詳細

## 1. 開発 PC の OS

一応 Windows 10 Creators Update `15063` も対応していますが、このハンズオンでは新しめの `16299` 以上に統一します。    

項目|値
----|----
あなたのマシンの OS の<br>現在のバージョンの確認方法|こちらを参照:「[Windows のバージョン確認方法](https://www.microsoft.com/ja-jp/safety/protect/ver_win.aspx)」の「ビルド番号」
入れるバージョン|10/16 に降ってきた Fall Creators Update 以上が適用されている (つまり`16299.15` 以上)<br>要は Windows 10 の最新の状態にしておけば間違いないです。(not Insider Preview 版)
アップデートの仕方|こちらを参照：「[Windows Update の利用手順 - Windows 10 の場合](https://www.microsoft.com/ja-jp/safety/protect/musteps_win10.aspx)」

![](https://fud.community.services.support.microsoft.com/Fud/FileDownloadHandler.ashx?fid=05415d7b-0480-4f8d-be0f-eeb055c558cd)

また、追加の操作として、「開発者モード」にしておいてください。    

`設定` > `更新とセキュリティ` > `開発者向け` > `開発者モード`

![](img/devmode.PNG)

## 2. HoloLens の OS

また、HoloLens の OS のバージョンも最新に上げておいてください。       
方法:

`Settings`  > `Update & Security` > `Device Update` > `Check for updates` ( > `Restart now (今すぐ再起動)`)

この作業を `Your device is up to date` (最新) となるまで繰り返してください。

### HoloLens を開発者モードに

開発PCと同様に、HoloLens も開発者モードにしましょう。
   
`Settings` > `Update & Security` > `For Developers` > `Developer mode` を ON にする

こちらの記事が詳しいです：    
[HoloLens チュートリアルの実機動作 by @Suna ](https://qiita.com/Suna/items/194989d8fa1d9bc3cc97)     
↓その記事の画像から        
![](img/holoDevMode.png)     


## 3. 開発 PC に入れる Visual Studio のバージョン

Visual Studio 2017 を入れます。

項目|値
----|----
あなたのマシンの VS の<br>現在のバージョンの確認方法|Visual Studio 2017 を開く > メニューバーの `ヘルプ` (一番右) > `Microsoft Visual Studio のバージョン情報` で出てきたウィンドウの、2行目に書いてあります (例：`Version 15.4.1`)
入れるバージョン|`15.4.x`
入れ方|こちらからダウンロード：[https://www.visualstudio.com/ja/downloads/](https://www.visualstudio.com/ja/downloads/)

## 5. Windows SDK を入れる

４番目の Unity よりも先にこちらを書きますね。

ホロレンズのアプリは Windows 10 アプリ(正確に言うと`UWPアプリ`)なので、開発にあたり、対応したバージョンのSDKが必要となります。

まず、Visual Studio 2017 のインストーラから「編集」を選びます。

そして必ず以下のSDKにチェックを入れて「変更」を押してください。
- `10.0.15063`
- `10.0.14393`

![VS installer](img/vsinstaller.jpg)

## 4. Unity

3D アプリを作るために、今回は Unity を使います。

最新のバージョンではなく、バージョン決め打ちの `2017.1.2`を使います。

ダウンロードはこちらから：    
[unity3d.com/.../archive](https://unity3d.com/get-unity/download/archive) の「Unity 2017.1.2」の「インストーラー」

![](img/unityin.png)

そして、

インストール時に、必ず

* `Windows Store .NET Scripting Backend` 
* `Windows Store IL2CPP Scripting Backend` 

の両方にチェックを入れてインストールしてください。

![unity](img/unityinstall.png)

## 
