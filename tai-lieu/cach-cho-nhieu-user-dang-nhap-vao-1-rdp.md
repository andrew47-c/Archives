---
description: '- Bài viết sẽ cho biết cách cho phép nhiều user đăng nhập vào 1 RDP'
---

# Cách cho nhiều user đăng nhập vào 1 RDP

### 💕Tổng Quan

* Bình thường, khi bạn đăng nhập vào 1 VPS thì người khác đang sử dụng VPS sẽ bị văng ra thế nên bài viết này sẽ giúp bạn cho phép nhiều người đăng nhập vào 1 VPS.

### ✨Chuẩn Bị

Trước khi bắt đầu bạn sẽ cần:

* 1 VPS (RDP)

### 📑Các bước thực hiện

Vui lòng đọc kỹ các thao tác sau:

1. Đăng nhập vào VPS.
2. Tổ hợp phím <mark style="color:blue;">**Win + R**</mark> để mở cửa sổ Run, nhập <mark style="color:red;">**gpedit.msc**</mark>.
3.  Theo đường dẫn <mark style="color:yellow;">**Computer Configuration > Administrative Templates > Windows Components > Remote Desktop Services > Remote Desktop Session Host > Connections**</mark>  và mở <mark style="color:green;">**Limit number of connections**</mark>                                                                                                                 Nếu bạn muốn tăng số lượng thì chọn **Enable** và chỉnh số lượng ở mục <mark style="color:orange;">**RD Maximum Connections allowed**</mark>&#x20;

    Nếu muốn không giới hạn thì chọn **Disable** sau đó chọn **Appy** và **Ok.**
4. Tiếp đó, mở <mark style="color:green;">**Restrict Remote Desktop services users to a single remote desktop services session**</mark> chọn **Disable** sau đó chọn **Apply** và **Ok**.
5.  Đóng cửa sổ gpedit và mở Server Manager chọn Manager > Add Roles and Features&#x20;

    <figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
6. Ấn **Next** > **Next** > **Next** tại **Server Roles** chọn **Remote Desktop Services** rồi ấn **Next** tại **Features** chọn **.NET Framework 3.5 Features** rồi ấn **Next** > **Next**, tại **Roles Services** chọn **Remote Desktop Connections Broker**, **Remote Desktop Licensing** và **Remote Desktop Session Host** rồi ấn **Next**, tại **Confirmation** chọn **Restart the destination server automatically if required** và chọn **Install.**

