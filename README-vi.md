# Samsung Temp Root Guide
[English ver](https://github.com/mydaudat1/Samsung-Temp-Root-Guide/blob/main/README.md)

[Bản tiếng Việt](https://github.com/mydaudat1/Samsung-Temp-Root-Guide/blob/main/README-vi.md)

Dạo gần đây temp root trên các máy chạy OneUI 8+ khá nổi, và với cương vị 1 đứa đã thử và đã brick - Tôi sẽ cho các bạn các tip.
## Lựa chọn app exploit:
- **Root My Galaxy**: Cổ điển, tôn trọng nhưng hỗ trợ rất ít máy.
- **Root My Galaxy Next**: Bản fork tốt nhất của RMG gốc. Có hỗ trợ thêm DirtyFlag và nhiều payload cho các máy. Đây có thể nói là repo active nhất nhóm. (root bằng
DirtyFlag có hỗ trợ KernelSU gốc). Tuy nhiên 1 số tính năng sẽ không hoạt động.
- **Root My Galaxy Forks (device specific)**: Các bản fork RMG chỉ tập trung vào 1 số mẫu máy nhất định.
- **DFRoot/DirtyFlag**: Dùng DirtyFlag để exploit, ít tính năng nhưng chất lượng. Và không hỗ trợ KernelSU gốc (sad).
## Các root manager:
Như nhau.
## QUAN TRỌNG: Cách phòng chống brick:
## 1: D2 Error:
- **Giải thích**: Nếu bạn để mật khẩu (PIN) trên máy thì Download Mode sẽ bị chặn và không thể vào được khi bị brick. 
- **Giải pháp**: Không để PIN.
## 2: Security Error:
- **Giải thích**: Vì temp root không gây ảnh hưởng đến bootloader nên khi bạn flash bất cứ thứ gì tác động đến bootloader máy bạn sẽ bị lỗi này. May mắn là bạn sẽ không bị Knox trip.
- **Giải pháp**: Flash ROM stock
## 3: Bootloop:
- **Giải thích**: Module bạn flash bị lỗi, superuser vừa làm gì đó lỗi.
- **Giải pháp**: Flash ROM stock. 
## 4: Mất data:
- **Giải thích**: Các data lưu cục bộ trên máy của bạn sẽ mất khi máy bị brick.
- **Giải pháp**: Backup trước khi làm điều gì.
## Xếp hạng các lỗi:
|Hạng|D2|Security Error|Bootloop|Data Lost|
|:---:|:---:|:---:|:---:|:---:|
|Cực nguy hiểm|✅️ (nếu brick)||||
|Nguy hiểm||✅️|✅️|||
|Bình thường|✅️||
|Khó chịu||||✅️|
## Hướng dẫn unbrick
## Trên Android:
**1: Chuẩn bị:**
- Một USB ổn định có thể truyền data.
- Một điện thoại Android.
- Máy đã vào sẵn Download Mode.
- ROM stock của máy.
- Brokkr
**Hướng dẫn**:
- **Bước 1:** Giải nén file ROM stock.
- **Bước 2:** Vào Brokkr, bật Auto Reboot.
- **Bước 3:** Ở ô AP, chọn file .tar có 2 chữ cái đầu trùng với tên ô (ví dụ: AP_XM510...)
- **Bước 4:** Ở ô BL, CP, CSC cũng tương tự (các máy Wi-fi only sẽ không có CP, nếu  không có thì bỏ ô CP đó)
- **Bước 5**: Ô USERDATA bỏ.
- **Bước 6**: Cắm USB vào máy cần unbrick và tiến hành flash (nên theo dõi máy để tránh máy tự tắt và khiến quá trình flash lỗi).
## Trên PC
- Một USB ổn định có thể truyền data.
- Một PC Windows.
- Máy đã vào sẵn Download Mode.
- ROM stock của máy.
- Odin.
## Hướng dẫn:
- **Bước 1:** Giải nén file ROM stock.
- **Bước 2:** Vào Odin, bật Auto Reboot.
- **Bước 3:** Ở ô AP, chọn file .tar có 2 chữ cái đầu trùng với tên ô (ví dụ: AP_XM510...)
- **Bước 4:** Ở ô BL, CP, CSC cũng tương tự (các máy Wi-fi only sẽ không có CP, nếu  không có thì bỏ ô CP đó)
- **Bước 5**: Ô USERDATA bỏ.
- **Bước 6**: Cắm USB vào máy cần unbrick và tiến hành flash.

**Lưu ý quan trọng**: Một số máy sẽ có CSC hỗn hợp (thường là OXX hoặc OLM). Bạn khi cài CSC này có thể cần phải setup vùng nhiều hơn. (ví dụ: XXV - Việt Nam sẽ nằm trong OLM - Hỗn hợp)
## Cách tải ROM stock:
- **Bước 1**: Copy dòng sau dấu chấm thứ 2 trong mục Build Number (Settings -> About this Phone -> Software Information).
- **Bước 2**: Vào [SamFW](https://samfw.com/)
- **Bước 3**: Ở mục "Enter device name or model code" paste dòng vừa copy
- **Bước 4**: Chọn CSC.
- **Bước 5**: Tải về.

Lưu ý: Nếu máy bạn đang ở màn hình Download Mode và không thể vào được OS thì **cách duy nhất** là phải tìm phần PRODUCT NAME và tự nhớ CSC. Vì vậy trước khi bạn làm điều gì thì luôn phải có ROM stock sẵn.

**Cách dò CSC:**
Trong mục Service provider software version (Settings -> About this Phone -> Software Information), 3 ký tự sau tên model của bạn chính là CSC. (ví dụ: Trong SAOMC_SM-G996B_OXM_XXV_15_0008 XXV/XXV,XXV/XXV. SM-G996B là tên model, OXM là mã CSC bạn cần tìm).
## Các keyword bạn nên tránh
- Direct Install 
- Anti-bootloop
- Hide
- Bootloader 
- Kernel
- SUFS modules
## Vấn đề bảo hành
Trong trường hợp máy bạn bị Security Error/bootloop nhưng còn bảo hành, bạn nên đảm bảo những mục này trong Download Mode:
- KG STATUS: PRENORMAL (00) (hoặc là CHECKING)
- WARRANTY VOID: 0x0 (0x0)

Nếu những dòng này trên máy bạn không giống. Rất có khả năng máy bạn đã bị Knox trip và sẽ bị từ chối bảo hành.

Khi bị chập eFuse Knox (Knox trip), cách duy nhất để lấy lại là **thay toàn bộ mainboard**.
## Tài nguyên
- ROM stock: [SamFW](https://samfw.com/)
- Brokkr: [GitHub](https://github.com/Gabriel2392/brokkr-flash)
- Odin: [SamFW blog](https://samfw.com/blog/download-odin-all-version)
- FRP Remove (paid): [SamFW tool service](https://samfw.com/frp)
## Bonus
Nếu máy bị D2 Error, bạn sẽ có thêm vài cách nữa: (chưa test)
## Fenrir:
**Fenrir** là 1 công cụ unbrick dành cho kỹ thuật viên Samsung. Bạn cần có tài khoản kỹ thuật viên Samsung để dùng nó.

**Cách vào**:

Ở màn hình D2:
- **Giữ xuyên xuốt**: nút nguồn
- **Bước 1**: 8 lần bấm tăng âm lượng.
- **Bước 2**: 5 lần giảm âm lượng.
- **Bước 3**: 9 lần tăng âm lượng.

Khi mã QR đã hiện:
- **Bước 1**: Chụp ảnh lại.
- **Bước 2**: Đẩy lên PC.
- **Bước 3**: Import ảnh vào Fenrir để lấy mã (8 chữ số)
- **Bước 4**: Bấm tăng âm lượng và giảm âm lượng để di chuyển đến chữ số cần nhập. Bấm nút nguồn để xác nhận.
- **Bước 5**: Di chuyển lên dòng "Done" và bấm nút nguồn để xác nhận.

## Chúc bạn suôn sẻ!
