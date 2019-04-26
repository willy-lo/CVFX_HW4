# CVFX_HW4

1.Take a sequence of moving-forward images in NTHU campus.

我們所拍攝的是操場的照片，那邊陽光比較好，所以覺得比較合適。

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/50.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/49.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/48.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/47.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/46.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/40.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/35.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/16.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/11.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/9.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/7.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/4.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/3.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/2.jpg)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/1.jpg)

2.Show feature extraction and matching results between two images

ORB 簡介:

ORB(ORiented Brief)特徵提取算法，其前身Brief，是由EPFL的Calonder在ECCV2010上提出了一種可以快速計算且表達方式為二進位編碼的描述子，主要思路就是在特徵點附近隨機選取若干點對，將這些點對的灰度值的大小，組合成一個二進位串，並將這個二進位串作為該特徵點的特徵描述子。BRIEF最大的優點在於速度快，然而其缺點也相當明顯，主要有以下幾方面：

1.不具有旋轉不變性；

2.不具有尺度不變性；

3.對抗噪聲性能差。

ORB就是試圖解決上述缺點中的1和3，即具有旋轉不變性的同時具有較好的抗噪能力。運算速度方面，ORB算法是SIFT算法的100倍，是SURF算法的10倍。

ORB算法解決旋轉不變性問題的思想：

ORB算法中採用了FAST作為特徵點檢測算子。在SIFT算法中，梯度直方圖的把第一峰值的方向設置為特徵點的主方向；如果次峰值的量度達到峰值的80%，則把第二個峰值的方向也設定為主方向，該算法相對更耗時。而在ORB的方案中，特徵點的主方向是通過矩（moment）計算得來。有了主方向之後，就可以依據該主方向提取Brief描述子。

ORB算法解決對噪聲敏感問題的方法：

由於ORB算法不直接使用像素點與點之間進行比較，而是選擇以該像素為中心的一個區域作為整一個比較對象，因此提高了抗噪聲的能力。

關於尺度不變性問題：

ORB沒有解決尺度不變性的問題（因為FAST本身就不具有尺度不變性）而且這類快速的特徵描述子，通常都是應用在實時的視頻處理中的，可以通過跟蹤還有一些啟發式的策略來解決尺度不變性的問題。

以下的比較圖則是有用到老師給的ORB來試試，覺得效果還蠻棒的!

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/2_.png)

3.Perform image alignment and generate infinite zooming effect

4.implement different feature extrators, e.g. SIFT, SURF, and compare the results

5.exploit creativity to add some image processing to enhance effect. You can use photoshop to do some effects, such as bluring or coloring.





