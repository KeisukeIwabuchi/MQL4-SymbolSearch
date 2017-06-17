# MQL4-SymbolSearch
MQL4で通貨ペアをいい感じに扱うためのモジュール


## Description
MT4は口座によって、同じ通貨ペアでも名称が異なる。  
例えばドル円であれば、USDJPY,USDJPYpro,USDJPYmなど。  
そのためプログラム中で"USDJPY"と指定しても、USDJPYのデータを正しく取得できない可能性がある。

これだけならまだプログラムで対応できるが、そもそも利用者が気配値表示に目的の通貨ペアを表示していない可能性もある。

そこでこのモジュールでは、口座ごとの名称の違いに対応しつつ、気配値表示に追加されていない通貨ペアでもデータを取得できるような実装をおこなった。


## Install
1. SymbolSearch.mqhをダウンロード
2. データフォルダを開き、/MQL4/Includes/mql4_modules/SymbolSearch/SymbolSearch.mqhとして保存


## Usage
SymbolSearch.mqhをincludeで読み込んで使用する。

### getSymbolInMarket
気配値表示に存在している通貨ペアの中から、引数に指定した通貨ペアの名称を取得する。
``` cpp
// USDとJPYを含む通貨ペアの名称を取得する
string symbol = SymbolSearch("USD", "JPY");
```
上記の例は、ドル円がUSDJPYの口座であればUSDJPYを、USDJPYproの口座であればUSDJPYproを返す。

もし該当の通貨ペアが気配値表示の中に存在せず、口座が提供する全銘柄一覧の中には存在している場合、気配値表示に追加した上で名称を返す。
