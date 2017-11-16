# HoloLens ハンズオン

## 環境

### 開発 PC や HoloLens にインストールしておくもの一覧表

このハンズオンをやるにあたり、準備していただきたい環境の一覧を載せます。    
(現在の入れてあるアプリのバージョンの確認手順や、具体的なインストール手順などは、表の下に書きます。)

＃|種類|項目|バージョン|ダウンロード先|当日までのアクション
----|----|----|----|----|----
1|OS|Windows 10|10/16 に振ってきた Fall Creators Update 以上が適用されている (つまり `16299.15` 以上)|Windows 設定アプリの「更新とセキュリティ」から|開発PCに要インストール
2|開発環境|Visual Studio 2017|`15.4.x`|[visualstudio.com/.../vs2017-relnotes](https://www.visualstudio.com/ja-jp/news/releasenotes/vs2017-relnotes)|開発PCに要インストール
3|開発環境|Unity|【決め打ち】<br>`2017.1.2`|[unity3d.com/.../archive](https://unity3d.com/get-unity/download/archive) の「Unity 2017.1.2」|開発PCに要インストール
4|SDK|Windows 10 SDK|【決め打ち】<br>`10.0.14393` と `10.0.10586`|Visual Studio のインストーラの「編集」から|開発PC(VS)に要インストール
5|SDK|MixedRealityToolkit-Unity for Unity|【決め打ち】<br>`v1.2017.1.2`|[github.com/Microsoft/.../Unitypackages](https://github.com/Microsoft/MixedRealityToolkit-Unity/tree/master/External/Unitypackages) の「HoloToolkit-Unity-v1.2017.1.2.unitypackage」|開発PCにダウンロードしておく
6|HoloLens 用アプリ|Holographic Remoting|(何でもいい)| **開発PCではなく、HoloLens に入れます。** HoloLens の Windows Store から「[Holographic Remoting](https://www.microsoft.com/ja-jp/store/p/holographic-remoting-player/9nblggh4sv40)」で検索してインストール| **HoloLens に** 要インストール

### 詳細

#### 1. 開発 PC の OS

一応 Windows 10 Creators Update `15063` も対応していますが、このハンズオンでは新しめの `16299` 以上に統一します。    

項目|値
----|----
あなたのマシンの OS の<br>現在のバージョンの確認方法|こちらを参照:「[Windows のバージョン確認方法](https://www.microsoft.com/ja-jp/safety/protect/ver_win.aspx)」の「ビルド番号」
入れるバージョン|10/16 に振ってきた Fall Creators Update 以上が適用されている (つまり`16299.15` 以上)
アップデートの仕方|こちらを参照：「[Windows Update の利用手順 - Windows 10 の場合](https://www.microsoft.com/ja-jp/safety/protect/musteps_win10.aspx)」
