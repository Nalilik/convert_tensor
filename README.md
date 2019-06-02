1. convert_tensor.py
 将三维数组image(h,w,c)转换为四维数组Tensor(b,h,w,a), 其中 c=b*a, 当c<b*a时将数组补零.
 效果示例如下:
![image](https://github.com/Nalilik/convert_tensor/blob/master/images/WechatIMG1099.jpeg)

 不能直接用reshape是因为我们要保留图像数据的完整性, 这时直接进行切片操作即可:image_hwc[:,:,i]
 输入h=2,w=2,c=5,a=2检查一下:
 image =
[[[ 0  1  2  3  4]
  [ 5  6  7  8  9]]

 [[10 11 12 13 14]
  [15 16 17 18 19]]]
Tensor =
[[[[ 0  1]
   [ 5  6]]
   
  [[10 11]
   [15 16]]]

 [[[ 2  3]
   [ 7  8]]

  [[12 13]
   [17 18]]]

 [[[ 4  0]
   [ 9  0]]

  [[14  0]
   [19  0]]]]

 转换成功.

