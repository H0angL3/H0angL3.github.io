# Logon event 4624

## About
Logon event được ghi lại khi có sự kiện đăng nhập. Trong windows, có hai loại đăng nhập:
- Local SAM account logon: đăng nhập và xác thực với tài khoản local.  
Lọai đăng nhập này được sử dụng trên máy trạm và log được lưu trữ trong máy trạm (workstation)
- Domain account logon: đăng nhập và xác thực với tài khoản trong domain. Các log đăng nhập được ghi lại trên Security log của máy chủ. Vì vậy, mặc dù các sự kiện đăng nhập tài khoản trong domain được tập trung tại DC, ta vẫn có thể tìm thấy các log này trên mọi hệ thống trong domain. (Làm rõ hơn)

## Mô tả event id 4624


!['event_4624'](img/winlogon/2020-11-02-eventid4624-examp.png "event id 4624")

### 1. Phần subject:
phần này xác định tài khoản yêu cầu đăng nhập. Phần này thường là Null hoặc là một trong các Service principal và thường chứa thông tin không hữu ích. Phần này chứa các trường
- Security ID
- Account Name
- Account Domain
- Logon ID

### 2. Phần Logon Information.
Phần này chứa các trường thông tin sau:  
- **Logon Type**: các giá trị có ý nghĩa như sau  

| Logon type | Mô tả |
| :---: | :---: |
| 2 | Xảy ra khi người dùng đăng nhập vào một máy tính cục bộ (bằng cách gõ tên và mật khẩu trong logon prompt. Type 2 xảy ra khi người dùng đăng nhập bằng tài khoản cục bộ hoặc domain. Tuy nhiên, đối với tài khoant domain thì loại này chỉ xuất hiện khi ) |
| 3 | đăng nhập qua Network (share file hoặc xác thực qua domain) |
| 4 | Batch: thông qua bat script. ví dụ schedual task |
| 5 | Service startup |
| 7 | 


