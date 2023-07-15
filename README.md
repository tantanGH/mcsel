# MCSEL.X

MACS Data File Selector for Human68k/X680x0

---

## About This

MACSデータファイルのセレクタ兼ローダです。「まくせる」と読みます（ぉ

 - ハイメモリ専用
 - ディスクからハイメモリに高速ダイレクトロード (SCSIの場合はTS16FILE.X必須)
 - PhantomX VDISK対応
 - エミュレータのホストファイルシステム対応
 - プレイリスト対応
 - リピート再生対応

<img src='images/mcsel1.png' width='800px'/>

---

## 動作環境

060turbo方式のハイメモリ(最低128MB程度、できれば384MB)が必須となりますので、以下のいずれかのハイメモリドライバが必要です。

1. 060turbo.sys

68060の場合はこちらをお勧めします。拡張モード(`-xm`)である必要はありませんが、`-ss`と`-dv`はつけたほうが良いでしょう。

2. TS16DRVp.X

68030の場合はこちらをお勧めします。特にオプションなどの指定はありません。

ハイメモリドライバが組み込まれていない場合は起動エラーとなります。

---

PCMドライバとして、PCM8A.X (256MB以上ハイメモリ対応版) または PCM8PP.X が必須です。
いずれも組み込まれていない場合は起動エラーとなります。

PCM8A.X の256MBハイメモリ対応改造版は以下の立花えりりん氏のGithubから入手できます。

[PCM8A.X 改造版](https://github.com/kg68k/pcm8a)

---

ハイメモリに対応した MACSDRV.X が組み込まれている必要があります。
また、必須ではありませんが MACSINFO.X をパスの通った場所に導入しておくことを推奨します。

---

## インストール

MCSELxxx.ZIP をダウンロードして、MCSEX.X をパスの通ったディレクトリにコピーします。

以下の2つの環境変数を設定しておきます。

- MCSEL_DATA_PATH ... MACSデータファイル(*.MCS)を格納してあるディレクトリ名をセミコロン(;)で区切って連結したもの。

- MCSEL_LIST_PATH ... MACSプレイリストファイル(*.MCL)を格納してあるディレクトリ名。1つだけ指定可能。

例：
    SET MCSEL_DATA_PATH=G:\MCS_DATA;H:\MCS_DATA;I:\MCS_DATA;J:\MCS_DATA;K:\MCS_DATA
    SET MCSEL_LIST_PATH=D:\MCS_LIST
