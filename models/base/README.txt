faster-whisper base（Systran/faster-whisper-base，MIT License）給手機版 Claude 沙盒用：沙盒連不到 huggingface 時，從這裡下載。
model.bin 拆成兩段（GitHub 單檔上限 100MB）：curl 下載 model.bin.partaa、model.bin.partab，用 cat model.bin.parta? > model.bin 接回。
同一資料夾放 config.json、tokenizer.json、vocabulary.txt，再 WhisperModel("這個資料夾路徑", device="cpu", compute_type="int8")。
model.bin sha256 開頭 d01c3014881c9c6f
