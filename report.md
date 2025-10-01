# Week 3 — Detectron2 安裝與降版
## 環境安裝步驟
本次作業使用Nvidia RTX 5060ti進行
1. 使用conda建立環境
```!bash
conda create -n myenv python=3.8.20
conda activate myenv
```
2. pillow降版
```
pip uninstall pillow
pip install pillow==9.0.1
```
3. 確認gcc是否安裝成功
```
gcc --version
```
4. 下載資料集，在NAS上的VIS_Lab/VIS_Lab共用(ALL) /99_Others/dataset/MSDAOD_dataset


## 模型訓練與推論結果截圖
### Foggy_Cityscapes
* MAX_ITER: 24000
第一次使用原本數據進行測試
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-10-01%20174827.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-28%20160518.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-28%20164708.png)
* MAX_ITER: 12000
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-10-01%20175032.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-28%20184552.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-28%20185031.png)
將MAX_ITER從24000修改為12000，可以發現在小物件辨識時(rider, motorcycle)，AP明顯降低
* MAX_ITER: 36000
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-10-01%20175124.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-30%20122407.png)
![alt text](https://github.com/andyw-by/Summer-Training-Week3/blob/main/images/%E8%9E%A2%E5%B9%95%E6%93%B7%E5%8F%96%E7%95%AB%E9%9D%A2%202025-09-30%20150057.png)
將MAX_ITER從24000修改為36000，AP與24000相比，反而稍微下降，從三次訓練可得到訓練時間與MAX_ITER成正比，而MAX_ITER並非越高越準確
