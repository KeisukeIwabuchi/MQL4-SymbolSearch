# MQL4-SymbolSearch
Module for handling currency pairs in MQL4.


## Description
Even the same currency pair has a different name in MT4.  
For example, for dollar yen, USDJPY, USDJPYpro, USDJPYm, etc.  
Therefore, even if you specify "USDJPY" in the program, there is a possibility that data of USDJPY may not be acquired correctly.  
If this is enough, it can still correspond with the program.  
However, there is a possibility that the user does not display the target currency pair in the MarketWatch.
Therefore, in this module, we implemented so that data can be acquired even for a pair of currencies which has not been added to the MarketWatch, while coping with the name difference for each account.


## Install
1. Download SymbolSearch.mqh
2. Save to the file /MQL4/Include/mql4_modules/SymbolSearch/SymbolSearch.mqh


## Usage
Includes SymbolSearch.mqh and use it.

### getSymbolInMarket
The name of the currency pair designated as the argument is acquired from the currency pair existing in the MarketWatch.
``` cpp
// USDとJPYを含む通貨ペアの名称を取得する
string symbol = SymbolSearch("USD", "JPY");
```
In the above example, USDJPY is returned if the dollar yen is an account of USDJPY, and USDJPYpro if it is an account of USDJPYpro.

If the corresponding currency pair does not exist in MarketWatch and it exists in the list of all stocks provided by the account, it is added to the indicator value display and the name is returned.
