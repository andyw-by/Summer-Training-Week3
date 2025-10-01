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
![alt text](image.png)
![alt text](<螢幕擷取畫面 2025-09-28 160518.png>)
![alt text](<螢幕擷取畫面 2025-09-28 164708.png>)
* MAX_ITER: 12000
![alt text](image-1.png)
![alt text](<螢幕擷取畫面 2025-09-28 184552.png>)
![alt text](<螢幕擷取畫面 2025-09-28 185031.png>)
將MAX_ITER從24000修改為12000，可以發現在小物件辨識時(rider, motorcycle)，AP明顯降低
* MAX_ITER: 36000
![alt text](image-2.png)
![alt text](<螢幕擷取畫面 2025-09-30 122407.png>)
![alt text](<螢幕擷取畫面 2025-09-30 150057.png>)
將MAX_ITER從24000修改為36000，AP與24000相比，反而稍微下降，從三次訓練可得到訓練時間與MAX_ITER成正比，而MAX_ITER並非越高越準確