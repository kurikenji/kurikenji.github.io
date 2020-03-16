---
title: "HHKB Alt Controlerの調べ"
date: 2020-03-16T22:46:12+09:00
draft: true
---

# TL;DR
HHKB Alt Controllerは大変素晴らしい。
入手、設定の仕方を残しておく。

# HHKB Alt Controllerとは

[Alternative Controller for HHKBのススメ](https://qiita.com/shela/items/62324752ff703bae3e74)

`Alternative Controller for HHKBとは、Happy Hacking Keyboard(HHKB)のコントローラを入れ替えることで全てのキーをプログラマブルにできるコントローラのこと。
キーボード自体をプログラマブルにすることで、OSあるいはAutoHotkeyやKarabinerなどのソフトウェアに依存せずどの環境でも同じ動作をさせることができるようになる。`

# 購入方法
[Topic: [TMK] Alt Controller Board for HHKB](https://geekhack.org/index.php?topic=71517.0)

# Bluetooth版の注意
リチウムイオンバッテリーは付属しないので、稼働実績を見て自分で入手する必要がある。
秋葉原の秋月商店に適当に並んでいるものでおk

# TMK or QMK
次世代のファームウェアがQMKと理解した。

# QMKのデプロイ環境
https://qiita.com/marksard/items/f381caf3ca981f307f64


```bash
git clone https://github.com/qmk/qmk_firmware
cd qmk_firmware
git submodule init
git submodule update
sudo ./util/wsl_install.sh
```

# QMKのデプロイ書き込み

```bash
make hhkb:default HHKB_RN42_ENABLE = yes
```

[Alternative Controller for HHKB を組み込んだ](https://toooybooox.blogspot.com/2017/03/alternative-controller-for-hhkb.html)

```cmd.exe
dfu-programmer.exe atmega32u4 erase --force
dfu-programmer.exe atmega32u4 flash unimap.hex
dfu-programmer.exe atmega32u4 reset
```

# キーカスタム
[Alternative Controller for HHKBのススメ] のshela氏のコンフィグをベースに個人カスタムして使っている。

