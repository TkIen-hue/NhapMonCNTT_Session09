## BÀI TẬP TRÊN LỚP HỆ THỐNG WEB LOGS
Đây là bài tập lọc các log chứa "ERROR" từ một file chứa nhiều logs.

Cách giải:
``` PowerShell
Get-ChildItem -Path ".\HeThong_Web_Logs" -Filter "*.log" -Recurse | Select-String -Pattern "ERROR" | Select-Object -ExpandProperty Line | Out-File -FilePath "bao_cao_loi.txt" -Append
```
``` Git Bash
find "HeThong_Web_Logs" -type f -name "*.log" -exec grep -h "ERROR" {} + >> "bao_cao_loi.txt"
```

Bảng so sánh khi dùng PowerShell và Git Bash:

|tiêu chí | PowerShell | Git Bash |
| :---: | :---: | :---: |
| Độ dài | Dài | Ngắn gọn |
| Tốc độ xử lý | Khá tốt, nhưng qua nhiều bước | Rất nhanh và tối ưu |
| Tính tương thích | Mặc định có sẵn trên mọi máy Windows | Có sẵn trong Git for Windows, phổ biến trên Linux/macOS |

![Hình ảnh](https://1drv.ms/i/c/810b967785280e83/IQCJcdBUCXX8T6aVEZ3osf2SAXl-8OgJhuD7L-qUWgze9K4?e=tESTlS)