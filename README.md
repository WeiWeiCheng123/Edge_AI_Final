# NTUST Edge AI (110-02) 期末專題報告_M11007309_鄭維新

## 1. 作品名稱：【智慧生活】─ 電梯小幫手

## 2. 摘要說明
情境上是在一台電梯前面有一個監視器，在監視器上部屬人工智慧的物件偵測去偵測監視器畫面中有沒有坐輪椅的人，假如有坐輪椅的人準備要搭電梯，電梯就提早進行動作，幫助不方便行動的人減輕壓力。

## 3. 系統簡介
![](https://i.imgur.com/8n6nGV3.png)

### 3.1 創作發想
創作的理念是想要幫助行動不便的人，讓他們的生活能夠更便利，使用了物件偵測的概念去偵測輪椅是否存在，預期系統完成後可以改善行動不便的人的生活，而且也可以減少可能需要有人在電梯協助的情況

### 3.2 硬體架構及軟體版本
本系統硬體及軟體為使用如下規格

- 型號: MSI GL62M 7RDX (筆記型電腦)
- CPU: Intel® Core™ i5-7300HQ 2.50GHz
- GPU: NVIDIA GTX1050 4GB
- RAM: 16GB
- OS: Ubuntu 20.04
- Python: 3.9.0

### 3.3 工作原理及流程
使用網路攝影機當作輸入，經過物件偵測的模型去判斷畫面內是否有坐輪椅的人即將要到電梯口等候電梯，假如有且電梯是可使用的話就會控制電梯抵達該樓層。

### 3.4 資料集建立方式
本系統資料集蒐集方式為使用手機進行錄影，再使用截圖的方式將影片中的影像擷取下來，最後使用LabelImg標註影像中的物件。

物件類別有People以及Wheelchair

### 3.5 模型選用與參數調整
本系統使用Yolov4-tiny作為物件偵測模型，沿用yolov4-tiny-custom.cfg，更動的訓練參數如下

- batch = 16
- Learning_rate = 0.00261
- max_batches = 4000
- filters = 21 (line 214, 265)
- classes = 2 (line 222, 271)

### 3.6 模型訓練
本模型訓練時長約為1小時40分鐘，訓練結果如圖所示。
![](https://i.imgur.com/hjJg4Gj.png)

## 4. 實驗結果
![](https://i.imgur.com/ugbdwPi.jpg)


## 5. 附錄
- [Colab程式](https://colab.research.google.com/drive/1WCjYBSQdmgv3JKr5lw2Oz5jyBQuhURsr?usp=sharing)
- [權重、資料集 GitHub](https://github.com/WeiWeiCheng123/edge\_AI\_Final)
- [Hackmd 文檔](https://hackmd.io/@weiwei0519/edge-AI-Final)

## 6. 參考資料
- [Darknet GitHub](https://github.com/AlexeyAB/darknet)
- [LabelImg GitHub](https://github.com/tzutalin/labelImg)
- [許哲豪，如何以Google Colab及Yolov4tiny (yolov4tiny)來訓練自定義資料集 ─ 以狗臉、貓臉、人臉偵測為例](https://omnixri.blogspot.com/2021/05/google-colabyolov4-tiny.html)
---
