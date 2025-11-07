# 🎬 VIDEO CUTTER TOOL - Hướng dẫn sử dụng

Công cụ cắt và ghép video đơn giản, nhanh chóng, và dễ sử dụng.

## 📖 Mục lục

- [Giới thiệu](#giới-thiệu)
- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)
- [Cài đặt](#cài-đặt)
- [3 cách sử dụng](#3-cách-sử-dụng)
  - [Cách 1: GUI (Khuyến nghị)](#cách-1-giao-diện-đồ-họa-gui)
  - [Cách 2: Interactive CLI](#cách-2-interactive-cli)
  - [Cách 3: Command Line](#cách-3-command-line-cli)
- [Định dạng thời gian](#định-dạng-thời-gian)
- [Chế độ xử lý](#chế-độ-xử-lý)
- [Tính năng nâng cao](#tính-năng-nâng-cao)
- [Ví dụ thực tế](#ví-dụ-thực-tế)
- [Xử lý lỗi](#xử-lý-lỗi)

---

## 🎯 Giới thiệu

**Video Cutter Tool** là công cụ Python giúp bạn:
- ✂️ Cắt nhiều đoạn từ một video dài
- 🔗 Tự động ghép các đoạn lại thành video mới
- ⚡ Xử lý nhanh với 3 chế độ tốc độ khác nhau
- 📥 Tải video từ YouTube
- ☁️ Tự động upload lên Google Drive

**Đặc điểm nổi bật:**
- 🪟 Giao diện đồ họa dễ dùng
- ⌨️ Command line mạnh mẽ cho chuyên gia
- 🎯 Interactive mode cho người mới
- 🔊 Tùy chọn bật/tắt âm thanh
- 📊 Hiển thị tiến trình chi tiết

---

## 📋 Yêu cầu hệ thống

### Bắt buộc:
- **Python 3.6+**
- **ffmpeg** (phần mềm xử lý video)

### Tùy chọn:
- **yt-dlp** (nếu muốn tải video từ YouTube)
- **rclone** (nếu muốn upload lên Google Drive)

---

## ⚙️ Cài đặt

### Ubuntu/Debian (Cài đặt tự động - Khuyến nghị)

Chỉ cần **1 dòng lệnh**:

```bash
curl -fsSL https://raw.githubusercontent.com/minhhlki/edit-cut-video/main/install.sh -o install.sh && chmod +x install.sh && ./install.sh
```

Script sẽ tự động:
- ✅ Cài Python 3, pip, ffmpeg
- ✅ Cài yt-dlp
- ✅ Cài rclone
- ✅ Tải xuống tất cả file
- ✅ Tạo thư mục cần thiết
- ✅ Mở interactive mode ngay

### Cài đặt thủ công

#### Linux/Ubuntu:
```bash
# Cài dependencies
sudo apt-get update
sudo apt-get install -y python3 python3-pip python3-tk ffmpeg

# Cài Python packages (tùy chọn)
pip3 install yt-dlp

# Clone repository
git clone https://github.com/minhhlki/edit-cut-video.git
cd edit-cut-video
```

#### macOS:
```bash
# Cài ffmpeg
brew install ffmpeg

# Cài Python packages (tùy chọn)
pip3 install yt-dlp

# Clone repository
git clone https://github.com/minhhlki/edit-cut-video.git
cd edit-cut-video
```

#### Windows:
1. **Cài Python 3**: Tải từ [python.org](https://www.python.org/downloads/)
2. **Cài ffmpeg**:
   - Tải từ [ffmpeg.org](https://ffmpeg.org/download.html)
   - Giải nén và thêm vào PATH
3. **Cài yt-dlp** (tùy chọn):
   ```bash
   pip install yt-dlp
   ```
4. **Tải tool**:
   ```bash
   git clone https://github.com/minhhlki/edit-cut-video.git
   cd edit-cut-video
   ```

---

## 🚀 3 cách sử dụng

### Cách 1: Giao diện đồ họa (GUI)

**Dành cho:** Mọi người - Dễ dùng nhất!

#### Khởi chạy:

**Linux/macOS:**
```bash
./run_gui.sh
# hoặc
python3 video_cutter_gui.py
```

**Windows:**
```bash
run_gui.bat
# hoặc
python video_cutter_gui.py
```

#### Các bước sử dụng:

1. **📹 Chọn video đầu vào**:
   - Cách A: Nhập URL YouTube → Nhấn "⬇️ Tải xuống"
   - Cách B: Nhấn "Chọn Video" để chọn file có sẵn

2. **✂️ Nhập đoạn cắt**:
   - Gõ các đoạn theo định dạng: `03:05-03:10|40:05-40:10|1:03:05-1:04:05`
   - Hoặc nhấn "Dán ví dụ mẫu" để xem mẫu

3. **✓ Kiểm tra định dạng**:
   - Nhấn "Kiểm tra định dạng" để xem trước
   - Tool sẽ hiển thị số đoạn và tổng thời lượng

4. **💾 Chọn nơi lưu**:
   - Nhấn "Chọn nơi lưu" để chọn vị trí và tên file đầu ra

5. **⚙️ Chọn chế độ xử lý**:
   - 🚀 **Fast** - Nhanh nhất (10-20x) nhưng có thể lệch ±1-2s
   - ⚡ **Balanced** - Cân bằng (3-4x, chính xác 100%) - **KHUYẾN NGHỊ**
   - 🎯 **Accurate** - Chậm nhất nhưng chính xác tuyệt đối

6. **🔊 Tùy chọn âm thanh**:
   - Tích vào "🔇 Tắt âm thanh" nếu muốn video không có tiếng

7. **🚀 Bắt đầu**:
   - Nhấn "BẮT ĐẦU CẮT VIDEO"
   - Theo dõi tiến trình trên thanh progress bar
   - Chờ hoàn thành!

---

### Cách 2: Interactive CLI

**Dành cho:** Người mới hoặc muốn được hướng dẫn từng bước

#### Khởi chạy:

```bash
python3 video_cutter_interactive.py
```

#### Tool sẽ hỏi bạn từng bước:

```
================================================
🎬 VIDEO CUTTER TOOL - Interactive Mode
================================================

------------------------------------------------------------
STEP 1: Video Source
------------------------------------------------------------
🔗 YouTube URL (Optional, press Enter to skip):
[Nhập URL YouTube hoặc Enter để bỏ qua]

📁 Video file path:
[Nhập đường dẫn file video]

------------------------------------------------------------
STEP 2: Segments to Cut
------------------------------------------------------------
Format: MM:SS-MM:SS|MM:SS-MM:SS|...
Example: 03:05-03:10|40:05-40:10|1:03:05-1:04:05

✂️  Segments:
[Nhập các đoạn cần cắt]

------------------------------------------------------------
STEP 3: Output Configuration
------------------------------------------------------------
💾 Output video path [video_cut.mp4]:
[Nhập tên file đầu ra hoặc Enter để dùng mặc định]

⚙️  Processing mode
  1. 🚀 Fast
  2. ⚡ Balanced (default)
  3. 🎯 Accurate

Your choice [1-3]:
[Chọn chế độ 1, 2, hoặc 3]

🔊 Remove audio (create silent video)? [y/N]:
[Nhập y để tắt âm thanh, hoặc Enter để giữ âm thanh]

------------------------------------------------------------
STEP 4: Google Drive Upload (Optional)
------------------------------------------------------------
📤 Upload to Google Drive after processing? [y/N]:
[Nhập y để upload, hoặc Enter để bỏ qua]

▶️  Start processing? [Y/n]:
[Enter để bắt đầu]
```

---

### Cách 3: Command Line (CLI)

**Dành cho:** Người có kinh nghiệm, muốn tự động hóa

#### Cú pháp cơ bản:

```bash
python video_cutter.py -i <video_đầu_vào> -s "<các_đoạn_cắt>" -o <video_đầu_ra>
```

#### Các tham số:

| Tham số | Bắt buộc | Mô tả |
|---------|----------|-------|
| `-i, --input` | ✅ | Đường dẫn video đầu vào |
| `-s, --segments` | ✅ | Các đoạn cần cắt (format: start-end\|start-end) |
| `-o, --output` | ✅ | Đường dẫn video đầu ra |
| `-t, --temp-dir` | ❌ | Thư mục tạm (mặc định: temp_segments) |
| `--mode` | ❌ | Chế độ: fast, balanced, accurate (mặc định: balanced) |
| `--no-audio` | ❌ | Tắt âm thanh |

#### Ví dụ:

```bash
# Cơ bản
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4

# Với chế độ Fast
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --mode fast

# Không có âm thanh
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --no-audio

# Kết hợp: Fast mode + No audio
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --mode fast --no-audio
```

---

## ⏱️ Định dạng thời gian

Tool hỗ trợ 2 định dạng:

### 1. MM:SS (Phút:Giây)
```
03:05    → 3 phút 5 giây
40:10    → 40 phút 10 giây
```

### 2. HH:MM:SS (Giờ:Phút:Giây)
```
1:03:05  → 1 giờ 3 phút 5 giây
2:30:45  → 2 giờ 30 phút 45 giây
```

### Định dạng đoạn cắt

Các đoạn được phân cách bằng dấu `|`:

```
start1-end1|start2-end2|start3-end3
```

**Ví dụ:**
```
03:05-03:10|40:05-40:10|1:03:05-1:04:05
```

Có nghĩa là:
- Đoạn 1: Từ 3:05 đến 3:10 (5 giây)
- Đoạn 2: Từ 40:05 đến 40:10 (5 giây)
- Đoạn 3: Từ 1:03:05 đến 1:04:05 (60 giây)
- **Tổng:** Video mới dài 1 phút 10 giây

---

## ⚡ Chế độ xử lý

Tool cung cấp 3 chế độ xử lý với tốc độ khác nhau:

### So sánh nhanh

| Chế độ | Tốc độ | Chính xác | Khi nào dùng |
|--------|--------|-----------|--------------|
| 🚀 **Fast** | Rất nhanh (10-20x) | ⚠️ ±1-2s | Test nhanh, video không quan trọng |
| ⚡ **Balanced** | Nhanh (3-4x) | ✅ 100% | **KHUYẾN NGHỊ** - Hầu hết trường hợp |
| 🎯 **Accurate** | Chậm nhất | ✅ 100% | Video CỰC quan trọng |

### Chi tiết từng chế độ

#### 🚀 Fast Mode

**Cách hoạt động:**
- Sử dụng `-c copy` (copy codec, không re-encode)
- Chỉ copy stream video/audio từ vị trí chỉ định
- Nhanh gấp 10-20 lần

**Ưu điểm:**
- ⚡ Cực kỳ nhanh
- 🔋 Tiết kiệm CPU
- 💾 File size nhỏ

**Nhược điểm:**
- ⚠️ Có thể lệch ±1-2 giây do keyframe

**Khi nào dùng:**
- Test xem trước
- Video game highlights
- Meme/funny clips
- Video không cần chính xác tuyệt đối

**Ví dụ:**
```bash
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --mode fast
```

#### ⚡ Balanced Mode (Khuyến nghị)

**Cách hoạt động:**
- Cắt nhiều đoạn song song (tối đa 4 luồng)
- Re-encode để đảm bảo chính xác 100%
- Tận dụng CPU multi-core

**Ưu điểm:**
- ⚡ Nhanh (gấp 3-4 lần so với Accurate)
- ✅ Chính xác 100%
- 🎯 Tối ưu cho video nhiều đoạn

**Nhược điểm:**
- 💻 Tốn CPU nhiều hơn

**Khi nào dùng:**
- **MỌI trường hợp thông thường**
- Video YouTube/TikTok
- Video quảng cáo
- Presentation clips

**Ví dụ:**
```bash
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4
# hoặc
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --mode balanced
```

#### 🎯 Accurate Mode

**Cách hoạt động:**
- Cắt tuần tự từng đoạn
- Re-encode với cài đặt tối ưu
- Đảm bảo chính xác tuyệt đối

**Ưu điểm:**
- ✅ Chính xác 100%
- 🔒 Ổn định nhất
- 💾 Chất lượng cao nhất

**Nhược điểm:**
- 🐢 Chậm nhất

**Khi nào dùng:**
- Video phim/phóng sự chuyên nghiệp
- Video cưới/kỷ niệm quan trọng
- Video cần chính xác từng frame

**Ví dụ:**
```bash
python video_cutter.py -i input.mp4 -s "03:05-03:10|40:05-40:10" -o output.mp4 --mode accurate
```

### Test case thực tế

**Video 15 phút, cắt 16 đoạn (mỗi đoạn 4 giây = 64 giây):**

| Chế độ | Thời gian xử lý | Cảm nhận |
|--------|----------------|----------|
| Fast | ~5-10 giây | 🤩 Wow! Nhanh! |
| Balanced | ~30-40 giây | 😊 Chấp nhận được |
| Accurate | ~120 giây (2 phút) | 😫 Lâu quá! |

---

## 🎨 Tính năng nâng cao

### 🔊 Tùy chọn âm thanh

Bạn có thể tắt âm thanh để tạo video im lặng:

**GUI:** Tích vào checkbox "🔇 Tắt âm thanh"

**CLI:**
```bash
python video_cutter.py -i input.mp4 -s "segments" -o output.mp4 --no-audio
```

**Khi nào dùng `--no-audio`:**
- Tạo video để thêm nhạc nền sau
- Video GIF-style không cần âm thanh
- Giảm kích thước file
- Video highlight im lặng

### 📥 Tải video từ YouTube

Tool tích hợp sẵn YouTube downloader.

**GUI:** Nhập URL vào ô "YouTube URL" → Nhấn "⬇️ Tải xuống"

**Interactive:** Tool sẽ hỏi URL YouTube trong STEP 1

**CLI riêng:**
```bash
# Tải video
python youtube_downloader.py https://www.youtube.com/watch?v=VIDEO_ID

# Tải và đặt tên file
python youtube_downloader.py https://www.youtube.com/watch?v=VIDEO_ID -o my_video.mp4

# Chỉ xem thông tin (không tải)
python youtube_downloader.py https://www.youtube.com/watch?v=VIDEO_ID --info
```

### ☁️ Upload lên Google Drive

Tool có thể tự động upload video đã xử lý lên Google Drive.

**Yêu cầu:** Cài rclone và cấu hình Google Drive

**Cách cài đặt rclone:**
```bash
# Linux
curl https://rclone.org/install.sh | sudo bash

# macOS
brew install rclone

# Windows
# Tải từ https://rclone.org/downloads/
```

**Cấu hình Google Drive:**
```bash
rclone config
# Làm theo hướng dẫn để thêm Google Drive
```

**Sử dụng:**
- **GUI:** Tích vào checkbox "📤 Upload lên Google Drive"
- **Interactive:** Chọn "y" khi được hỏi về upload

### 🪟 Build file EXE cho Windows

Nếu bạn muốn tạo file `.exe` độc lập cho Windows:

```bash
# Cài PyInstaller
pip install pyinstaller

# Build file EXE
pyinstaller --onefile --windowed --name="VideoCutter" video_cutter_gui.py
```

File EXE sẽ nằm trong thư mục `dist/VideoCutter.exe`

**Lưu ý:** Người dùng vẫn cần cài ffmpeg riêng, hoặc bạn có thể đóng gói ffmpeg.exe cùng với VideoCutter.exe

---

## 📝 Ví dụ thực tế

### Ví dụ 1: Tạo video highlight từ video dài

**Tình huống:** Bạn có video webinar 2 giờ, muốn cắt ra các phần quan trọng

```bash
python video_cutter.py \
  -i webinar_full.mp4 \
  -s "00:30-01:00|15:20-16:45|45:00-47:30|1:30:00-1:32:15" \
  -o webinar_highlights.mp4 \
  --mode balanced
```

### Ví dụ 2: Cắt bỏ quảng cáo

**Tình huống:** Video có quảng cáo, bạn chỉ muốn phần nội dung

```bash
python video_cutter.py \
  -i video_with_ads.mp4 \
  -s "00:00-05:00|05:30-15:30|16:00-20:00" \
  -o video_no_ads.mp4
```

### Ví dụ 3: Workflow YouTube → Cắt → Upload

```bash
# Bước 1: Tải video từ YouTube
python youtube_downloader.py https://www.youtube.com/watch?v=VIDEO_ID -o youtube_video.mp4

# Bước 2: Cắt video
python video_cutter.py \
  -i downloads/youtube_video.mp4 \
  -s "00:30-01:00|05:00-05:30|10:00-11:00" \
  -o highlights.mp4 \
  --mode fast \
  --no-audio

# Bước 3: Upload (nếu cần)
rclone copy highlights.mp4 gdrive:Video_Cutter_Uploads/
```

**💡 Mẹo:** Dùng GUI hoặc Interactive mode để làm tất cả trong một lần!

### Ví dụ 4: Tạo video compilation

**Tình huống:** Ghép nhiều best moment từ video dài

```bash
python video_cutter.py \
  -i game_recording.mp4 \
  -s "03:45-04:15|12:30-13:00|25:15-26:00|45:30-46:15" \
  -o best_moments.mp4 \
  --mode fast
```

### Ví dụ 5: Video im lặng để thêm nhạc nền

```bash
python video_cutter.py \
  -i raw_footage.mp4 \
  -s "01:00-01:30|05:00-05:45|10:00-10:30" \
  -o silent_video.mp4 \
  --no-audio
```

---

## 🛠️ Xử lý lỗi

### Lỗi: "ffmpeg not found" hoặc "ffmpeg chưa được cài đặt"

**Nguyên nhân:** ffmpeg chưa được cài đặt hoặc không có trong PATH

**Giải pháp:**
```bash
# Kiểm tra ffmpeg
ffmpeg -version

# Ubuntu/Debian
sudo apt-get update
sudo apt-get install ffmpeg

# macOS
brew install ffmpeg

# Windows
# Tải từ https://ffmpeg.org/download.html
# Giải nén và thêm vào PATH
```

### Lỗi: "Không tìm thấy file video"

**Nguyên nhân:** Đường dẫn file không đúng

**Giải pháp:**
- Kiểm tra lại đường dẫn
- Sử dụng đường dẫn tuyệt đối
- Đảm bảo file tồn tại

```bash
# Kiểm tra file có tồn tại không
ls -la /path/to/video.mp4
```

### Lỗi: "Invalid time format"

**Nguyên nhân:** Định dạng thời gian không đúng

**Giải pháp:**
- Sử dụng định dạng: `MM:SS` hoặc `HH:MM:SS`
- Đảm bảo có dấu `-` giữa start và end
- Đảm bảo có dấu `|` giữa các đoạn

**Đúng:**
```
03:05-03:10|40:05-40:10
```

**Sai:**
```
03:05 - 03:10 | 40:05 - 40:10  # Có dấu cách thừa
3:5-3:10  # Thiếu số 0 đầu
```

### Lỗi: "End time must be greater than start time"

**Nguyên nhân:** Thời gian kết thúc nhỏ hơn thời gian bắt đầu

**Giải pháp:** Đảm bảo `end_time > start_time`

**Sai:**
```
03:10-03:05  # End (3:10) < Start (3:05) - SAI!
```

**Đúng:**
```
03:05-03:10  # Start (3:05) < End (3:10) - ĐÚNG!
```

### Lỗi: "yt-dlp not found"

**Nguyên nhân:** yt-dlp chưa được cài đặt

**Giải pháp:**
```bash
pip3 install yt-dlp
```

### Lỗi: "rclone not found"

**Nguyên nhân:** rclone chưa được cài đặt hoặc chưa cấu hình

**Giải pháp:**
```bash
# Cài rclone
curl https://rclone.org/install.sh | sudo bash

# Cấu hình Google Drive
rclone config
```

### Video bị lệch âm thanh

**Nguyên nhân:** Có thể do Fast mode

**Giải pháp:** Sử dụng Balanced hoặc Accurate mode

```bash
python video_cutter.py -i input.mp4 -s "segments" -o output.mp4 --mode balanced
```

### Tool chạy chậm

**Nguyên nhân:** Đang dùng Accurate mode

**Giải pháp:** Chuyển sang Balanced hoặc Fast mode

```bash
# Balanced - Nhanh gấp 3-4 lần
python video_cutter.py -i input.mp4 -s "segments" -o output.mp4 --mode balanced

# Fast - Nhanh gấp 10-20 lần (có thể lệch ±1-2s)
python video_cutter.py -i input.mp4 -s "segments" -o output.mp4 --mode fast
```

---

## 💡 Mẹo và thủ thuật

1. **Kiểm tra định dạng trước**: Dùng GUI và nhấn "Kiểm tra định dạng" để xác nhận trước khi cắt

2. **Chọn chế độ phù hợp**:
   - Test/Preview → Fast
   - Thông thường → Balanced
   - Quan trọng → Accurate

3. **Backup video gốc**: Luôn giữ bản gốc trước khi cắt

4. **Sử dụng SSD**: Xử lý video nhanh hơn trên ổ SSD so với HDD

5. **Đóng app khác**: Đóng các ứng dụng nặng khác khi xử lý video để tăng tốc

6. **Test với đoạn ngắn**: Test với 1-2 đoạn ngắn trước khi cắt nhiều đoạn

7. **Dùng thời gian tròn**: Cắt tại thời điểm tròn giây (00:30, 01:00) sẽ nhanh hơn

---

## 📊 Output mẫu

Khi chạy tool, bạn sẽ thấy output như sau:

```
🎬 Bắt đầu cắt video từ: video_dai.mp4
📊 Tổng số đoạn cần cắt: 3

⚡ BALANCED MODE (Nhanh + Chính xác)
🔊 Âm thanh: Bật (Giữ nguyên)

🔄 Đang cắt 3 đoạn song song với 3 luồng...

✅ [1/3] Đoạn 1: 03:05.000 → 03:10.000 (Độ dài: 00:05.000)
✅ [2/3] Đoạn 2: 40:05.000 → 40:10.000 (Độ dài: 00:05.000)
✅ [3/3] Đoạn 3: 01:03:05.000 → 01:04:05.000 (Độ dài: 01:00.000)

✅ Đã cắt xong 3 đoạn
⚡ Thời gian cắt: 25.3s

🔗 Đang ghép các đoạn lại với nhau...
✨ Hoàn thành! Video đã được lưu tại: video_ngan.mp4

📊 Thống kê:
   - Thời gian cắt: 25.3s
   - Thời gian ghép: 1.2s
   - Tổng thời gian: 26.5s
   - Tốc độ xử lý: 3.4x realtime
   - Tổng thời lượng video mới: 01:10.000

🧹 Đã xóa các file tạm
```

---

## 📞 Hỗ trợ

Nếu bạn gặp vấn đề hoặc có câu hỏi:
- Tạo issue trên GitHub
- Kiểm tra lại phần [Xử lý lỗi](#xử-lý-lỗi)

---

## 📄 License

MIT License - Tự do sử dụng và chỉnh sửa

---

**🎬 Chúc bạn cắt video vui vẻ! ✨**
