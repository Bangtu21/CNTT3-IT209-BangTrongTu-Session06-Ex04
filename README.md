## 1. Tạo và cấp quyền cho script
File: `loop-monitor.sh`

Script ghi thời gian hiện tại vào `/tmp/monitor.log` mỗi 5 giây.

Cấp quyền thực thi: `chmod +x loop-monitor.sh`

## 2. Khởi chạy tiến trình nền
Lệnh: `nohup ./loop-monitor.sh > /dev/null 2>&1 &`

Tìm PID: `pgrep -f loop-monitor.sh`

PID: `108185`

## 3. Kiểm tra tiến trình và log

Kiểm tra tiến trình: `ps aux | grep loop-monitor.sh`

Kiểm tra log: `tail -n 10 /tmp/monitor.log`

Kết quả cho thấy thời gian được ghi liên tục mỗi 5 giây.

## 4. Dừng tiến trình

Lệnh: `kill -15 108185`

Kiểm tra lại: `ps aux | grep loop-monitor.sh`

Tiến trình `loop-monitor.sh` đã được dừng bằng tín hiệu SIGTERM.
