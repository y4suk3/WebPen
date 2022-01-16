# WebPen

https://github.com/topics/xss-poc

## インジェクション系のまとめ

|  脆弱性  |  インターフェース  |  悪用手口  | データの終端  |
| ---- | ---- |---- |---- |
|  XSS  |  HTML  | JavaScriptなどの注入  | `<` `"` など  |
|  SQLi  |  SQL  | SQL 命令の注入 | `'` など  |
|  RCE  |  シェルスクリプト  | コマンドの注入  | `;` `\|` など  |
|  HTTPヘッダ・インジェクション  |  HTTP  | HTTP レスポンスヘッダの注入  | 改行 |
|  メールヘッダ・インジェクション  |  sendmail コマンド  | メールヘッダ、本文注入・改変 | 改行 |

## PHP
PHP は C言語で開発された言語

### 入力値検証
+ バイナリセーフ   
バイナリセーフとは、バイナリデータ（どんなバイト列であってもデータ）を正しく扱うことができる関数   
典型的には値ゼロのバイト（ヌルバイト、PHP言語では \0 ）   
ヌルバイトを正しく扱えない関数をバイナリセーフではない関数という。
+ ヌルバイト攻撃   
C言語および Unix や Windows の API では、ヌルバイトを文字列の終端と見なる取り決めがされている。   
C言語で開発された PHP言語などのバイナリセーフな関数は、nullバイト（「\0」、「\x00」などの終端文字とされている文字列）を含めることでセキュリティチェックをくぐり抜けてしまう。

|  ASCII文字  |  説明  |  URLエンコード  |
| ---- | ---- | ---- |
| NUL | ヌル文字 | %00 |
| CR	| キャリッジリターン |	%0D |
 	 	
	 	
