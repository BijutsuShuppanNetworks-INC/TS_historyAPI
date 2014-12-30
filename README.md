TS_historyAPI
=============
# ajax先にクローラーが来るかどうか検証

http://gc.bnw-me.info/test1/  
http://gc.bnw-me.info/test2/  
http://gc.bnw-me.info/test3/


## 概要
historyAPIでのブラウザバックの挙動調査

## 検証内容
- ajaxで取得したコンテンツ一覧から遷移し、再び一覧に戻った時に任意の場所に戻れるか(通信あり)
- 同一ページ内でjavascriptによってコンテンツ書き換えを行ったとき、ブラウザバックで最初の状態に戻れるか(通信なし)
- ~~これを簡単に実装するフレームワークがあるかどうか(余裕があれば)~~ historyAPIの実装そんなに難しくなかった
 
## 検証先URL
http://bijutsushuppannetworks-inc.github.io/TS_historyAPI/

## 懸念事項
- iOS safariではリロードが発生しないブラウザバック(Back-Forwad Cache)が発生する。
- iOS6とiOS7ではbfcacheの保持が異なる。
- bfcaheでもイベントを発火させるにはwindow.onpageshow イベントを使う。  
参考：  
http://blog.oogatta.com/entry/20121228/1356696182  
https://developer.mozilla.org/ja/docs/Using_Firefox_1.5_caching
- iOS chromeでhistoryのstateをjsonで記述するとエラーになるかも。後ほど検証。

