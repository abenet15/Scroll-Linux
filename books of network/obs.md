---

# 📓 Note: Samsung Phone Camera → OBS (Minimal)

## 1. Phone Setup

- Install **IP Webcam** (Play Store).
- Start server → note URL (e.g. `http://192.168.1.42:8080/video`).

## 2. Ubuntu Setup

```bash
sudo apt update
sudo apt install v4l2loopback-dkms ffmpeg v4l-utils
sudo modprobe v4l2loopback exclusive_caps=1 vid_nr=2 card_label="PhoneCam"
```

## 3. Pipe Stream

```bash
ffmpeg -i http://<phone-ip>:8080/video \
  -vf format=yuv420p,scale=640:480,fps=30 \
  -pix_fmt yuv420p \
  -f v4l2 /dev/video2
```

*(keep terminal open)*

## 4. OBS Setup

- Add **Video Capture Device**.
- Select `/dev/video2 (PhoneCam)`.
- Match resolution/FPS to FFmpeg settings.

---

✅ That’s the entire chain: **Phone → FFmpeg → v4l2loopback → OBS**.

Would you like me to also prepare a **troubleshooting mini‑scroll** (common errors like timeout, pixel format mismatch, black screen) so you can keep it alongside this note? 
