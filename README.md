# Net Open Location Finder With Obstacles
當時稚嫩的大學專題，來自ICCAD 2017年B題目。

+ 學生：陳佳琳、劉湘怡
+ 指導教授：鄭維凱
+ 完整書面報告請見：[pdf](https://github.com/k66inthesky/NetOpenLocationFinderWithObstacles/blob/main/%E5%AE%8C%E6%95%B4%E6%9B%B8%E9%9D%A2%E5%A0%B1%E5%91%8A.pdf)

### 題目：
> 起源： 
在 IC 設計繞線（routing）時，為了節省成本及避免障礙物干擾，希望連接的
線路能越短越好。以此為背景，此專題實作的過程我們討論了各種可能，運
用資料結構及演算法，以及曾經學過的數學方法，達到線路之成本最小化。 
![介紹](https://github.com/k66inthesky/NetOpenLocationFinderWithObstacles/assets/45890492/e37e8225-cd67-4761-af0c-bc39b03cb566) 
+ 此專題配合 2017 國際積體電路競賽 ICCAD 之 Problem B 做延伸。 
+ 將所有給定的藍色矩形相連接、並避免經過灰色矩形。 
+ 層與層間用給定的 via 或自訂 via 連接。 
+ 根據題目給的公式算出 cost，cost 越小分數越高。

### 目標：
+ Overall Cost = ∑Cost(Pq) 
+ 若 Pq是 H-line 或 V-line，Cost(Pq)即為 H-line 或 V-line 的長度。 
+ 若 Pq是 via，Cost(Pq) = Cv。 
+ 目標是將 overall cost 最小化

+ 其中還有一些路徑是不合法(invalid)的，如：
![介紹-不合法的](https://github.com/k66inthesky/NetOpenLocationFinderWithObstacles/assets/45890492/fdc796d0-9e8f-4c3f-ab33-5021d3bb0bb5)


我們針對此題目提出一些原創方法，詳見：[pdf](https://github.com/k66inthesky/NetOpenLocationFinderWithObstacles/blob/main/%E5%AE%8C%E6%95%B4%E6%9B%B8%E9%9D%A2%E5%A0%B1%E5%91%8A.pdf)

### 實驗結果：
|版本|層數|合法矩形個數|非法矩形個數|總Path|共使用Via數|總ViaCost|總Cost|總執行時間| 
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Case1-init|3|1503|414|53,095,736|2|20|53,095,736|204|
|Case1-final|x|x|x|4326|45|450|4776|94|
|Case2-init|5|4518|4773|515,899,298|4|120|515,899,298|18,669|
|Case2-final|x|x|x|39,806|186|5580|45,386|1019|
|Case3-init|5|4450|4762|4|20|x|x|x|
|Case3-final|x|x|x|12,691|901|4505|18,196|939|

### 結論：
在 via 之 cost 小於 100、layer 層數超過三層的情況下，雖然使用大量 via 造成 via 之 cost 增加，但整體 cost 比起層層之間只有一條 via來的好。
