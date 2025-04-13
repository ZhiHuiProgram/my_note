QQ：手机存储→Android(系统文件夹）→data→com.tencent.mobileQQ→Tencent→MobileQQ→你的QQ号命名的文件夹→ptt
微信：将语音收藏，手机将收藏的语音转存为笔记，转发到文件助手，在微信存储文件夹搜索silk后缀文件

# 默认
```
ffmpeg -i input.ogg output.mp3
```

# 🎛 带音质设置的版本：
```
ffmpeg -i input.ogg -codec:a libmp3lame -qscale:a 2 output.mp3
参数解释：
-codec:a libmp3lame：使用 LAME 编码器（最常见的 mp3 编码器）
-qscale:a：控制音质，范围是 0（最好）到 9（最差）
推荐值：
2：接近原音质
5：适中
7-9：体积小但音质下降
```
