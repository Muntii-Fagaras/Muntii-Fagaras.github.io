# 貢献の方法

## このプロジェクトのビルド方法

### xmakeでプロジェクトのビルドをする方法

1. xmakeを使いビルドします。
[xmake](https://xmake.io/#/guide/installation)にアクセスし、お使いの環境にあったxmakeをインストールします。

2. インストールが完了したら本プロジェクトのsrcディレクトリへ移動して、

```shell
xmake project -k vsxmake
```

とコマンドを実行すると、visual studioのslnが含まれたファイルが生成されます。

3. 出来上がったファイルをダブルクリックすると、ビルドができます。

### Linux編

Linuxでのビルド方法についてご紹介します。  
本項目では、Arch Linuxをベースに解説します。  

[Building a simple SDL2 app from scratch](https://mesonbuild.com/GuiTutorial.html)を参考に構築します。  

1. まずはビルドに必要な**meson,gcc,gdb**を

```shell
sudo pacman -S meson gcc gdb
```

インストールします。
2. 任意のディレクトリへ移動して

```shell
git clone https://github.com/312k/
cd gui-base/src
```

として、本プロジェクトをクローンします。そして、クローンしたディレクトリへ移動します。
3. mesonはSDL2をWrapDBによって依存関係をダウンロードできるので、

```shell
mkdir subprojects
meson wrap install sdl2
```

subprojectsにSDL2をダウンロードします。
4. ビルド先のディレクトリを

```shell
meson setup builddir
```

準備します。
5. プロジェクトをコンパイルします。

```shell
meson compile -C builddir
```

### Windows 11編

#### Meson編
1. Mesonとninjaを

```shell
pip install meson ninja
```

pipからダウンロードします。

2. pipのパスを通していない場合通します。
3. mesonでVisual Studioのsln

```shell
meson setup --backend vs builddir
```

を生成します
4. 生成したファイルから、slnを起動します。

#### Visual Studio編

本プロジェクトは、Visual Studio 2022を採用しています。
1. まずは、本プロジェクトをGithubからクローンします。

```shell
git clone https://github.com/312k/gui-base.git
```

2. クローンしたら、srcディレクトリに移動します。
3. srcディレクトリ内の**src.sln**をダブルクリックします。
4. 起動したら、CTRL+F5でデバッグなしで実行できます。
## clang-formatの方法

```shell
$ clang-format *.cpp *.hpp *.h class/*.cpp class/*.hpp
```
## このプロジェクトのソースコードの解説

### クラスについて

クラスの使用方法については、class_desc内のファイルをご覧ください。

#### Visual Studio Code編
本プロジェクトは、Visual Studio Codeを使ってもビルドができます。  
1. msys2からgccとmakeをインストールする。
　　本プロジェクトではgccとmakeを使います。
2. src直下をVisual Studio Codeのプロジェクトに追加してください。  
3. CTRL+ALT+F5キーでビルドができます。