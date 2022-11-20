# load_fileクラス
## コンストラクタ
```cpp
load_file{
	std::string file_path
}
```

## メソッド

### chk

#### ソースコード

```cpp
bool load_file::chk(std::string path) {
}
```

#### 使い方

第一引数に、確認したいファイルのパスを渡してください。戻り値として、ファイルが存在すれば、true、しなければ、falseを返してくれます。