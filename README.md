# 時間序列預測
## 目的
前陣子由於疫情大爆發，各國疫情嚴峻之際每日都有人受到感染。
雖然台灣目前已經稍微控制住，但全球仍然籠罩在肺炎之中。
想要針對感染人數較多之地區進行預測，主要針對感染數、康復數及死亡數各總數進行預測， 
藉由增加預測的準確率，可以在醫療資源配置及政策制定上有所幫助。
## 資料集
* 使用Kaggle上之covid_19_data.csv資料集

* 資料集描述:
資料集內涵蓋一月底至五月之資料，共八欄，分別為資料號(SNo)、洲別(Province/State)、日期(ObservationDate)、國家(Country/Region)、確診感染數(Confirmed)、死亡數(Deaths)、康復數(Recovered)。
資料集內涵許多國家及地區，考量中國及美國人口較多，受感染人數亦較多，因此針對資料集進行預處理，篩選以進行確診感染數(Confirmed)、死亡數(Deaths)、康復數(Recovered)之預測。
* 原始資料集:
![](https://i.imgur.com/qQW3bNw.png)

* 預處理後之資料集:
![](https://i.imgur.com/1opc8AS.png)


* 分別繪出一月底至五月底間死亡數、復原數及感染數
![](https://i.imgur.com/O6CaSmi.png)
## 資料處理步驟
* 匯入資料集並將資料做正規化
* 將訓練資料與測試資料拆分
* 搭建LSTM模型
* 分別繪出測試及訓練的預測圖
* 繪出loss變化圖並評估模型
## LSTM模型
* LSTM模型中隱藏層有10個神經元，輸出層2個神經元
* 損失函式採用均方誤差(mean_squared_error)
* 優化演算法採用Adam
* 模型採用500個epochs，batch size為128
![](https://i.imgur.com/RgDGIL6.png)
## 感染數
![](https://i.imgur.com/FaTGQqd.png)
## 死亡數
![](https://i.imgur.com/cQnEl05.png)
## 復原數
![](https://i.imgur.com/Eb36qTA.png)
## 模型評估
|                                      | 模型評估值|
|:------------------------------------------|------------:|
| 感染數                   |        0.00012954730482306331|
| 死亡數                     |        0.0001794082927517593
| 復原數                  |       0.00032710458617657423|

