# cstdio
* cstdio[meta header]

`<cstdio>`ヘッダでは、標準入出力のための機能を定義する。これらの機能は、`std`名前空間に属することを除いてC言語の標準ライブラリ`<stdio.h>`ヘッダと同じである。


## 型

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`size_t`](/reference/cstddef/size_t.md) | 符号なし整数型 | |
| `FILE` | ストリームの制御に必要な情報を持つオブジェクト型 | |
| `fpos_t` | ファイルの全ての位置にアクセスするための配列以外の完全オブジェクト型 | |


## マクロ

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`NULL`](/reference/cstddef/null.md) | ヌルポインタ定数に展開されるマクロ | |
| `_IOFBF` | 入出力を完全にバッファリングする指定のための整数定数 | |
| `_IOLBF` | 入出力を行バッファリングする指定のための整数定数 | |
| `_IONBF` | 入出力をバッファリングしない指定のための整数定数 | |
| `BUFSIZ` | バッファサイズを表す整数定数 | |
| `EOF`    | ファイルの終端であることを表す`int`型の整数定数 | |
| `FOPEN_MAX`    | 実装によって保証されるファイルを開ける最低限の数を表す整数定数 | |
| `FILENAME_MAX` | 実装によって保証されるファイル名の最大の長さを表す整数定数 | |
| `L_tmpnam` | `tmpnam()`関数によって作られた一時ファイル名を保持する似に必要な長さを表す整数定数 | |
| `SEEK_SET` | ファイルの先頭位置を指定するための整数定数 | |
| `SEEK_CUR` | ファイルの現在位置を指定するための整数定数 | |
| `SEEK_END` | ファイルの終端を指定するための整数定数 | |
| `TMP_MAX`  | `tempnam()`関数によって生成できる一時ファイル名の、実装が保証する最低限の数を表す整数定数 | |
| `strerr`   | 標準エラーを表す`FILE*`型の式 |
| `strin`    | 標準入力を表す`FILE*`型の式 |
| `strout`   | 標準出力を表す`FILE*`型の式 |


## ファイル操作

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `remove`   | ファイルを削除する | |
| `rename`   | ファイル名を変更、ファイルを移動する | |
| `tmpfile`  | 一時ファイルを生成する | |
| `tempname` | 一時ファイル名を生成する | |
| `fclose`   | ファイルを閉じる | |
| `fopen`    | ファイルを開く | |
| `fflush`   | ファイルをフラッシュする | |
| `fprintf`  | 書式を指定してファイルに出力する | |
| `fscanf`   | 書式を指定してファイルから入力する | |
| `vfprintf` | 可変引数リスト`va_list`を使用し、書式を指定してファイルに出力する | |
| `vfscanf`  | 可変引数リスト`va_list`を使用し、書式を指定してファイルから入力する | C++17 |
| `fgetc`    | ファイルから1文字入力する | |
| `fgets`    | ファイルからN文字入力する | |
| `fputc`    | ファイルに1文字出力する | |
| `fputs`    | ファイルにN文字出力する | |
| `fread`    | ファイルからN文字読み込む | |
| `fwrite`   | ファイルにN文字書き込む | |
| `fgetpos`  | ファイルの現在位置を取得する | |
| `fseek`    | ファイルの現在位置を移動する | |
| `fsetpos`  | ファイルの現在位置を設定する | |
| `ftell`    | ファイルの現在位置を取得する | |
| `rewind`   | ファイルの現在位置を先頭に戻し、エラーや終端判定をクリアする | |
| `clearerr` | エラーをクリアする | |
| `feof`     | ファイルが終端に到達したか判定する | |
| `ferror`   | ファイルストリームがエラー状態かを判定する | |
| `perror`   | システムエラーメッセージを出力する | |


## 標準入出力

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `printf`  | 書式を指定して標準出力に出力する | |
| `scanf`   | 書式を指定して標準入力から入力する | |
| `vprintf` | 可変引数リスト`va_list`を使用し、書式を指定して標準出力に出力する | |
| `vscanf`  | 可変引数リスト`va_list`を使用し、書式を指定して標準入力から入力する | |
| `getc`    | ストリームから1文字入力する | |
| `getchar` | 標準入力から1文字入力する | |
| `putc`    | ストリームに1文字出力する | |
| `putchar` | 標準出力に1文字出力する | |
| `puts`    | 標準出力に文字列を出力する | |
| `uungetc` | 入力ストリームに1文字戻す | |


## 文字列入出力

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `snprintf`  | 書式と文字数を指定して、文字列領域に出力する | |
| `sprintf`   | 書式を指定して文字列領域に出力する | |
| `sscanf`    | 書式を指定して文字列領域から入力する | |
| `vsnprintf` | 可変引数リスト`va_list`を使用し、書式と文字数を指定して、文字列領域に出力する | |
| `vsprintf`  | 可変引数リスト`va_list`を使用し、書式を指定して文字列領域に出力する | |
| `vsscanf`   | 可変引数リスト`va_list`を使用し、書式を指定して文字列領域から入力する | |


## バッファ操作

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `serbuf`  | 入出力用のバッファを設定する | |
| `setvbuf` | 戦略を指定して入出力用のバッファを設定する | |


## 参照
- [P0063R3 C++17 should refer to C11 instead of C99](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0063r3.html)
- [P0175R1 Synopses for the C library](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0175r1.html)