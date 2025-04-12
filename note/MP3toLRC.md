##下载
```
pip install torch torchaudio
pip install git+https://github.com/guillaumekln/faster-whisper
```
##python代码
```
from faster_whisper import WhisperModel

# 加载模型，使用默认的 CPU 计算
model = WhisperModel("base", compute_type="int8")

# 音频文件路径
audio_file = "your_audio.mp3"

# 获取转录结果
segments, _ = model.transcribe(audio_file, beam_size=5)

# 输出结果
for segment in segments:
    print(f"[{segment.start:02d}:{segment.end:02d}] {segment.text}")
```
