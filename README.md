# 台師大深度學習HW1
使用YOLOv8m模型偵測Waldo，並在複雜背景及大尺寸圖像中尋找Waldo在哪裡。  
## STEP 1 Roboflow
datasets在roboflow網站參數⬇️    

Preprocessing:  
No preprocessing steps were applied.  
Augmentation:  
Crop: 0% Minimum Zoom, 12% Maximum Zoom  

datasets的訓練跟驗證集分成8:2  

![training Validation Split](roboflow.png)
下載完後手動加入無Waldo的圖片(負樣本)共30張進training set  
**最後train model圖片數量:**  
**training set:128張**  
**validation set:25張**

## STEP 2 Model training in VS Code
執行train_waldo.py  
重要路徑如下:  
Best.pt path: runs\train_aug_final2\weights\best.pt  
predict graph path: runs\train_aug_final2\predict  
## STEP 3 Predict Image
利用train_waldo.py底下comment掉的CLI指令推論測試集中2000張並挑選conf大於0.7以上的照片

## Installation
### 1. Clone this Repository
```
git clone https://github.com/MingChun234/NTNU_DL_HW1
cd NTNU_DL_HW1
```
### 2. Install dependencies
此專案使用Conda建立執行環境
```
conda create -n yolov8 python=3.10 -y
conda env create -f environment.yml
conda activate yolov8
```
### 3. Run train_waldo.py
```
python train_waldo.py
```

