## 下载
```
pip install torch torchaudio
pip install git+https://github.com/guillaumekln/faster-whisper
```
## python代码
```
from faster_whisper import WhisperModel

# 选择模型
model = WhisperModel("tiny", compute_type="int8")  # CPU 可用

# 音频路径
audio_path = "your_audio.mp3"

# 转录
segments, _ = model.transcribe(audio_path)

# 保存为 .lrc 文件
with open("output.lrc", "w", encoding="utf-8") as f:
    for segment in segments:
        # 转换时间为 LRC 格式 [mm:ss.xx]
        minutes = int(segment.start // 60)
        seconds = int(segment.start % 60)
        milliseconds = int((segment.start - int(segment.start)) * 100)
        timestamp = f"[{minutes:02}:{seconds:02}.{milliseconds:02}]"
        f.write(f"{timestamp} {segment.text.strip()}\n")

print("已生成 LRC 文件：output.lrc")
```
