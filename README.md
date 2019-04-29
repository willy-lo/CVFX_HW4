# CVFX_HW4

1.Take a sequence of moving-forward images in NTHU campus.

我們所拍攝的是資電館8樓的照片，但一開始我們是在跑道做，後來發現操場跑道不好做，所以我們換成資電館8樓的照片。

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/1.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/2.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/3.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/4.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/5.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/6.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/7.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/8.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/9.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/10.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/11.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/12.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/13.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/14.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/15.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/16.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/17.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/18.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/19.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/20.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/21.JPG)
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/Photo/22.JPG)


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

3.對抗雜訊性能差。

ORB就是試圖解決上述缺點中的1和3，即具有旋轉不變性的同時具有較好的抗噪能力。運算速度方面，ORB算法是SIFT算法的100倍，是SURF算法的10倍。

ORB算法解決旋轉不變性問題的思想：

ORB算法中採用了FAST作為特徵點檢測算子。在SIFT算法中，梯度直方圖的把第一峰值的方向設置為特徵點的主方向；如果次峰值的量度達到峰值的80%，則把第二個峰值的方向也設定為主方向，該算法相對更耗時。而在ORB的方案中，特徵點的主方向是通過矩（moment）計算得來。有了主方向之後，就可以依據該主方向提取Brief描述子。

ORB算法解決對雜訊敏感問題的方法：

由於ORB算法不直接使用像素點與點之間進行比較，而是選擇以該像素為中心的一個區域作為整一個比較對象，因此提高了抗雜訊的能力。

關於尺度不變性問題：

ORB沒有解決尺度不變性的問題（因為FAST本身就不具有尺度不變性）而且這類快速的特徵描述子，通常都是應用在實時的視頻處理中的，可以通過跟蹤還有一些啟發式的策略來解決尺度不變性的問題。

以下的比較圖則是有用到老師給的ORB來試試，覺得效果還可以，因為我可能兩張圖距離格比較遠，有些地方沒有對到。

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/ORB.JPG)

3.Perform image alignment and generate infinite zooming effect

4.implement different feature extrators, e.g. SIFT, SURF, and compare the results

SIFT與SURF的共同點：

SIFT與SURF為了實現不同影像中相同場景的匹配，主要包括三個步驟：

1、尺度空間的建立

2、特徵點的提取

3、利用特徵點周圍鄰近區域的資訊生成特徵描述

4、特徵點匹配

  兩幅影像中的物體一般只是旋轉和縮放的關係，加上影像的亮度及對比度的不同，要在這些條件下要實現物體之間的匹配，SIFT演算法的發明者想到只要找到多於三對物體間的匹配點就可以通過射影幾何的理論建立它們的一一對應。

  如何找到這樣的匹配點呢？SIFT與SURF作者的想法是首先找到影象中的一些“穩定點”，這些點是一些特殊的點，不會因為視角的改變、光照的變化、雜訊的干擾而消失，比如角點、邊緣點、暗區域的亮點以及亮區域的暗點。這樣如果兩幅影像中有相同的景物，那麼這些穩定點就會在兩幅影像的相同景物上同時出現，這樣就能實現匹配。因此，SIFT/SURF演算法的基礎是穩定點。

  SIFT/SURF提取的穩定點，首先都要求是區域性極值。但是，當兩個物體的大小比例不一樣時，大影像的區域性極值點在小影像的對應位置上有可能不是極值點。於是SIFT/SURF都採用影像金字塔的方法，每一個截面與原影象相似，這樣兩個金字塔中就有可能包含大小最近似的兩個截面了。這樣找到的特徵點會比較多，經過一些處理後濾掉一些相對不穩定的點。

  接下來如何去匹配相同物體上對應的點呢？SIFT/SURF的作者都想到以特徵點為中心，在周圍鄰近區域內統計特徵，將特徵附加到穩定點上，生成特徵描述子。在遇到旋轉的情況下，作者決定找出一個主方向，然後以這個方向為參考座標進行後面的特徵統計，就解決了旋轉的問題。
共同的大問題有以下幾個：

1、為什麼選用高斯金字塔來做特徵提取？

為什麼是DOG的金字塔？因為它接近LOG，而LOG的極值點提供了最穩定的特徵，而且DOG方便計算（只要做減法。）

2、Hessian矩陣為什麼能用來篩選極值點？

SIFT先利用非極大抑制，再用到Hessian矩陣進行濾除。SURF先用Hessian矩陣，再進行非極大抑制。SURF的順序可以加快篩選速度麼？（Hessian矩陣濾除的點更多？）

3、為什麼採用梯度特徵作為區域性不變特徵？
這與人的視覺神經相關。採用梯度作為描述子的原因是，人的視覺皮層上的神經元對特定方向和空間頻率的梯度相應很敏感，經過SIFT作者的一些實驗驗證，用梯度的方法進行匹配效果很好。

4、為什麼可以採用某些特徵點的區域性不變特徵進行整幅影像的匹配？
從直觀的人類視覺印象來看，人類視覺對物體的描述也是區域性化的，基於區域性不變特徵的影像識別方法十分接近於人類視覺機理，通過區域性化的特徵組合，形成對目標物體的整體印象，這就為區域性不變特徵提取方法提供了生物學上的解釋，因此區域性不變特徵也得到了廣泛應用。
另外，影像中的每個區域性區域的重要性和影響範圍並非同等重要，即特徵不是同等顯著的，其主要理論來源是Marr的計算機視覺理論和Treisman的特徵整合理論，一般也稱為“原子論”。該理論認為視覺的過程開始於對物體的特徵性質和簡單組成部分的分析，是從區域性性質到大範圍性質。

SIFT/SURF都是對特徵點的區域性區域的描述，這些特徵點應該是影響重要的點，對這些點的分析更加重要。所以在區域性不變特徵的提取和描述時也遵循與人眼視覺注意選擇原理相類似的機制，所以SIFT/SURF用於匹配有效果。

SIFT與SURF不同點的比較：
	
![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/point.JPG)

SIFT與SURF效果的比較：

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/effect.JPG)

由此可見，SIFT在尺度和旋轉變換的情況下效果最好，SURF在亮度變化下匹配效果最好，在模糊方面優於SIFT，而尺度和旋轉的變化不及SIFT，旋轉不變上比SIFT差很多。速度上看，SURF是SIFT速度的3倍。


SIFT模擬圖:

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/SIFT.JPG)

SURF模擬圖:

![image](https://github.com/willy-lo/CVFX_HW4/blob/master/NTHU_campus/SURF.JPG)

從這兩個方法下製造出來的圖，我發現SIFT的效果比較好，SURF的效果比較差，因為我們是在操場上拍的，所以亮度方面是差不多的，所以SURF的特點沒有特別展現出來!

5.exploit creativity to add some image processing to enhance effect. You can use photoshop to do some effects, such as bluring or coloring.






