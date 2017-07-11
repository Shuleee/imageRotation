# imageRotation
## 实现图片的自动翻转：
### 两种方案：
#### 1.	调用c程序（.c, shell, jpegtran(无损转换图片)）

包括2个文件：jpegexiforient.c 和 exifautotran（脚本程序）
以及安装jpegtran（sudo apt-get install jpegtran）

编译：gcc -o jpegexiforient jpegexiforient.c
执行：exifautotran *.jpg

100张图片（1m30s）
#### 2.	使用imagemagick
    convert img_5035.jpg -format %[EXIF:Orientation] info:
查询图片的orientation参数

    convert img_5035.jpg -auto-orient img_5035_rotate.jpg
转换为正常显示
      
      mogrify -path new -auto-orient *.JPG
批处理命令
100张图片（1m30s）
