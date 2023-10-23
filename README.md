
# MR射擊遊戲 (｡:.ﾟヽ(>´∀`)ﾉﾟ.:｡)   
#### 第七小組成員    
* C110118210 黃志輝(組長)  Godot3D基礎學習/玩家/敵人設計
* C110118246 戴裕桓  視覺辨識方案抉擇/連接/實作
* C110118249 林彥辰  3D模型/動畫方案抉擇
* C110118256 尤重又  Godot3D基礎學習/場景設計
### 專題簡介 (300字以上) (。･ﾟ･(つд`ﾟ)･ﾟ･)   
```
由於一些人不喜歡用滑鼠遊玩3D遊戲，
他們認為滑鼠操作太過複雜、不熟悉。
利用便宜且容易獲得的Webcam拍攝肢體動作能更直覺的操控，
而且不需要hololens、類似的專業的設備也可進行遊玩。

遊戲目前的構想是：
玩家是一名法師，可以用手勢來施放魔法擊退怪物，
通過擊敗敵人逐漸地加強自身、獲得新的能力，
出現更多強大的對手、更多的遊戲體驗。

工具：
使用Mediapipe手部辨識模型偵測使用者的手部:
根據傳回的關鍵點座標來移動視角，
再利用座標之間的角度、距離辨識手勢，
進行不同的攻擊施放、其他的動作與功能等。

遊戲主體在Godot上建構:
通過Godot靈活的場景系統與節點結構、
可以繼承、實例化場景的功能，
用更直觀、快速的方式組織遊戲。

程式腳本在VSCode上用C#編譯:
由於Godot本身的編譯器不夠完善，
所以使用官方推薦的VSCode以及提供的功能擴展。
```
```mermaid
gantt
    title work process
    研擬計畫:a1, 2023-09-11, 1d
    任務分配:a2, after a1, 4d
    視覺辨識方案抉擇:a3, after a2, 7d
    Godot3D基礎學習:a4, after a2, 14d
    3D模型/動畫方案抉擇:a5, after a2, 14d
    場景設計:a6, after a4 & a5, 14d
    玩家/敵人設計:a7, after a4 & a5, 14d
    視覺辨識連接/實作:a8, after a6 & a7, 14d
    測試:a9, after a8, 7d
```
## PERT/CPM 圖
![CPM](關鍵路竟.jpg "CPM")

## 系統需求：
> * 功能性需求：
> 1. 通過攝影機傳輸畫面給Mediapipe，以此將讀取到的手部座標輸入操控角色視角。
> 2. 玩家可以使用不同的手勢召喚出不同的法術。
## FDD
![FDD](FDD.png "FDD")
> 4. 玩家在關卡限定的條件(ex:時間、擊中數量)達成時，可以解鎖後續的遊戲關卡、能力等等。
> * 非功能性需求：
> 1. 反應時間：在變更手部座標後，在1/60秒內可以做出反應。
> 2. 使用性：對於一個習慣3D遊戲的玩家，在5分鐘內可以正常射擊、轉動視角，1小時內可以習慣。
> 3. 可靠度：除了玩家本身失誤之外，針對手勢偵測誤動作少於10%。
