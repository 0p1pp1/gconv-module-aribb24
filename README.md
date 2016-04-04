# デジタルTV用文字コード(ARIB STD-B24)のiconv変換モジュール

## ビルド

```
./autogen.sh
mkdir build
cd build
../configure [--prefix=....]
make
sudo make install
```

`/etc/profile.d/gconv-module-aribb24.sh`により、GCONV_PATHが自動設定される。
(iconv(1)参照)
