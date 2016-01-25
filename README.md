我們原本想利用spark的MLlib來跑kaggle的titanic

https://spark.apache.org/docs/1.2.0/mllib-ensembles.html

但是嘗試了很久，一直有問題在

所以我們最後決定改善data visulization的效能

由於資料量過大，讀取firebase資料可能造成時間延遲的問題

我們把資料先存在本地端，以增加讀取的速度

想辦法改善loading過久的問題

不過在本地端用twstat-template測試的時候一直有點問題

所以最後的版本就沒有使用

更改的部份在index.hbs的230～390行

<pre>
$(function(){
  $.getJSON('datas.json',function(data){
      $.each( data, function( key, val ) {
        /*put data to chart*/
      });
		}).error(function(){
      console.log('error');
    });
});
</pre>
