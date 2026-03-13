## I. Khái quát về mối đe doạ và tấn công:
### 1. Một số khái niệm:
- Mối đe doạ (Threat): Là bất kỳ hành động nào có thể gây hư hại đến các tài nguyên (phần cứng, phần mềm, database, files, data, hạ tầng vật lý,...)
- Điểm yếu (Weakness):
    - Là một lỗi hoặc khiếm khuyết tồn tại trong hệ thống.
    - Các hệ thống luôn tồn tại điểm yếu.
- Lỗ hổng (Vulnerability): Là bất kỳ điểm yếu nào trong hệ thống cho phép mối đe doạ có thể gây tác hại.

### 2. Quan hệ giữa mối đe doạ và lỗ hổng:
- Các mối đe doạ thường khai thác một hoặc một số lỗ hổng đã biết để thực hiện các cuộc tấn công phá hoại.
- Nếu tồn tại một lỗ hổng trong hệ thống, sẽ có khả năng một mối đe doạ trở thành hiện thực.
- Không thể triệt tiêu được hết các mối đe doạ nhưng có thể giảm thiểu các lỗ hổng, qua đó giảm thiểu khả năng bị tấn công.

### 3. Các mối đe doạ thường gặp:
Khổng phải tất cả các mối đe doạ đều là độc hại, một số là cố ý, một số có thể là ngẫu nhiên/vô tình.
- Phần mềm độc hại.
- Hư hỏng phần cứng hay phần mềm.
- Attacker ở bên trong/ngoài.
- Mất trộm thiết bị.
- Tai hoạ thiên nhiên.
- Gián điệp công nghiệp.
- Khủng bố.
- ...

### 4. Các lỗ hổng:
#### a) Tồn tại trong cả bảy vùng của nền tảng Công nghệ Thông tin:
- Lỗ hổng trong vùng người dùng.
- Lỗ hổng trong vùng máy trạm.
- Lỗ hổng trong vùng mạng LAN.
- Lỗ hổng trong vùng LAN-to-WAN.
- Lỗ hổng trong vùng mạng WAN.
- Lỗ hổng trong vùng truy nhập từ xa.
- Lỗ hổng trong vùng hệ thống/ứng dụng.

#### b) Tồn tại trong hệ điều hành và các phần mềm ứng dụng:
- Lỗi tràn bộ đệm (Buffer Overflows).
- Không kiểm tra đầu vào (Unvalidated Input).
- Các vấn đề với điều khiển truy nhập (Access-control Problems).
- Các điểm yếu trong xác thực, trao quyền (Weakness in Authetication, Athorization).
- Các điểm yếu trong hệ mật mã (Weakness in Cryptographic practices).

### 5. Tấn công (Malicious Attacks):
- Một cuộc tấn công vào hệ thống máy tính hoặc tài nguyên mạng được thực hiện bằng cách khai thác lỗ hổng trong hệ thống.
- Tấn công = Mối đe doạ + Lỗ hổng

#### a) Các loại tấn công:
Gồm bốn loại chính:
- Giả mạo (Fabrications): Giả mạo thông tin để đánh lừa user thông thường.
- Chặn bắt (Interceptions): Liên quan đến việc nghe trộm đường truyền và chuyển hướng thông tin để dùng trái phép.
- Gây ngắt quãng (Interruptions): Gây ngắt kênh truyền thông ngăn cản việc truyền dữ liệu.
- Sửa đổi (Modifications): Liên quan đến việc sửa đổi thông tin trên đường truyền hoặc dữ liệu file.

#### b) Hai kiểu tấn công:
##### Tấn công chủ động (Active attacks):
Tấn công chủ động là đột nhập (instrution) về mặt vật lý.
- Sửa đổi dữ liệu trên đường truyền.
- Sửa đổi dữ liệu trong file.
- Giành quyền truy nhập trái phép vào máy tính hoặc hệ thống mạng.

##### Tấn công thụ động (Passive attacks):
- Không gây ra thay đổi trên hệ thống.
- Nghe trộm.
- Giám sát lưu lượng trên đường truyền.

#### c) Một số dạng tấn công điển hình:
- Tấn công vào mật khẩu.
- Tấn công bằng mã độc.
- Tấn công từ chối dịch vụ.
- Tấn công giả mạo địa chỉ, nghe trộm.
- Tấn công kiểu phát lại và người đứng giữa.
- Tấn công bằng bom thư và thư rác.
- Tấn công sửa dụng Backdoor.
- Tấn công kiểu Social Engineering.
- Tấn công phishing, pharming.

## II. Các công cụ hỗ trợ tấn công:
- Công cụ tấn công (Attack tools): Các công cụ phần cứng, phần mềm hoặc các kỹ thuật hỗ trợ giúp attacker tấn công vào các hệ thống máy tính hoặc tài nguyên mạng.
- Một số công cụ và kỹ thuật hỗ trợ tấn công:

### 1. Công cụ quét lỗ hổng (Vulnerability scanners):
- Thu thập các thông tin về điểm yếu/lỗ hổng đã biết của hệ thống máy tính hoặc mạng.
- Gửi những thông điệp được tạo đặc biệt để kiểm tra điểm yếu/lỗ hổng đến hệ thống máy tính cần rà quét. Nếu có phản hồi thì có điểm yếu.
- Attacker dùng kết quả rà quét điểm yếu/lỗ hổng để quyết định dạng tấn công có khả năng thành công cao nhất.
#### Một số công cụ quét lỗ hổng cho admin:
- Microsoft Baseline Security Analyzer:
    - Rà quét các lỗ hổng an ninh trong Windows và các phần mềm của Microsoft.
    - Phân tích tình trạng lỗ hổng và có hướng dẫn khắc phục.
- Nessus Vulnerability Scanner:
    - Quét hệ thống tìm kiếm lỗ hổng, điểm yếu.
    - Độc lập với các nền tảng:
- Acunetix Web Vulnerability Scanner: Rà quét các ứng dụng web/trang web để tìm các lỗ hổng.

### 2. Công cụ quét cổng dịch vụ (Port scanners):
- Các cổng TCP/IP, UDP nằm trong khoảng từ 0 đến 65535:
    - Các cổng 0 - 1024 là các cổng chuẩn.
    - Cổng lớn hơn 1024 là các cổng tuỳ gán.
- Attacker thường dùng công cụ quét cổng để nhận dạng các điểm yếu trong hệ thống.
- Công cụ quét cổng kết nối đến máy tính để xác định cổng nào được mở và có thể truy nhập vào máy tính, từ đó xác định được dịch vụ/ứng dụng nào đang chạy trên hệ thống.
> - Cổng 80/443 mở: Dịch vụ web đang chạy.
> - Cổng 25 mở: Dịch vụ email SMTP đang chạy.
> - Cổng 1433 mở: Máy chủ database MS SQL đang chạy.
> - Cổng 53 mở: Dịch vụ DNS đang chạy.
> - ...
- Nguyên tắc tối thiểu cho các cổng được mở:
    - Đóng tất cả các cổng không dùng.
    - Chỉ mở những cổng có dịch vụ cần thiết cho user.
- Một số công cụ quét cổng:
    - Nmap
    - Portsweep
    - Advanced Port Scanner
    - Angry IP Scanner
    - Superscan
    - NetScanTools

### 3. Công cụ nghe lén (Sniffers):
- Công cụ nghe lén cho phép bắt các gói tin khi chúng được truyền trên mạng.
- Công cụ nghe lén có thể là module phần cứng, phần mềm hoặc kết hợp.
- Các thông tin nhạy cảm nếu không được mã hoá thì có thể bị attacker nghe lén khi được truyền từ client đến server và bị lợi dụng.
- Một số công cụ cho phép bắt gói tin truyền:
    - Tcpdump
    - Pcap/Wincap
    - IP Tools
    - Wireshark

### 4. Công cụ ghi phím gõ (Keyloggers):
- Là một dạng công cụ giám sát có thể bằng phần cứng hoặc phần mềm có khả năng ghi lại mọi phím user gõ và lưu vào một file.
- File đã ghi có thể được gửi cho attacker theo địa chỉ chỉ định trước hoặc copy trực tiếp.
- Người quản lý có thể cài đặt Keylogger vào máy tính nhân viên để theo dõi hoạt động.
- Cài đặt Keyloggers:
    - Bằng phần cứng: Thường được cài như một khớp nối kéo dài giữa máy tính và dây phím.
    - Bằng phần mềm: Attacker có thể tích hợp công cụ Keylogger vào một phần mềm thông thường và lừa user cài vào máy tính.

## III. Các dạng tấn công phá hoại:
### 1. Tấn công vào mật khẩu:
#### a) Khái niệm:
Là dạng tấn công nhằm đánh cắp mật khẩu và thông tin tài khoản.
- Tên user và mật khẩu không được mã hoá có thể bị đánh cắp trên đường truyền từ client đến server.
- Tên user và mật khẩu có thể bị đánh cắp qua các dạng tấn công XSS hoặc Social Engineering (lừa đảo, bẫy cung cấp thông tin).
- Nếu attacker có tên user và mật khẩu thì có thể đăng nhập vào tài khoản và thực hiện các thao tác như user bình thường.

#### b) Các dạng tấn công:
- Tấn công dựa trên từ điển (Dictionary attacks): User có xu hướng chọn mật khẩu là các từ đơn giản có trong từ điển cho dễ nhớ, attacker thử các từ có tần suất sử dụng cao.
- Tấn công vét cạn (Brute force): Sử dụng tổ hợp các ký tự và thử tự động:
    - Thường dùng với các mật khẩu đã mã hoá.
    - Attacker dùng tổ hợp ký tự, sau đó mã hoá với cùng thuật toán hệ thống dùng và so sánh chuỗi mã hoá với chuỗi mà mật khẩu thu thập được. Nếu hai bản mã trùng nhau thì tổ hợp ký tự là mật khẩu.

#### c) Phòng chống:
- Chọn mật khẩu đủ mạnh.
- Định kỳ thay đổi mật khẩu.

#### d) Một số công cụ khôi phục mật khẩu:
- Password Cracker
- Ophcrack
- Offline NT Password & Registry Editor
- PC Login Now
- L0phtCrack
- John the Ripper

### 2. Tấn công bằng mã độc:
Có thể gồm một số dạng:
- Lợi dụng các lỗ hổng về lập trình, lỗ hổng cấu hình hệ thống để chèn và thực hiện mã độc trên hệ thống nạn nhân:
    - Buffer Overflow
    - Tấn công lợi dụng lỗi không kiểm tra đầu vào:
        - SQL Injection
        - Tấn công cript kiểu XSS, CSRF
- Lừa user tải, cài và thực hiện các phần mềm độc hại:
    - Các phần mềm Adware, Spyware
    - Virus
    - Trojan

#### Tấn công lợi dụng lỗi không kiểm tra đầu vào:
- Các dữ liệu đầu vào (Input data) cần được kiểm tra để đảm bảo đạt các yêu cầu về định dạng và kích thước.
- Các dạng dữ liệu nhập điển hình cần kiểm tra:
    - Các trường dữ liệu text.
    - Các lệnh được truyền qua URL để kích hoạt chương trình.
    - Các file âm thanh, hình ảnh hoặc đồ hoạ do user hoặc các tiến tình khác cung cấp.
    - Các đối số đầu vào trong lệnh.
    - Các dữ liệu từ mạng hoặc các nguồn không tin cậy.
- Attacker có thể kiểm tra các dữ liệu đầu vào và thử tất cả khả năng để khai thác.
- Một số dạng tấn công:
    - Cố tình nhập dữ liệu quá lớn hoặc sai định dạng để gây lỗi cho ứng dụng, có thể làm ngừng hoạt động.
    - Chèn mã SQL để thực hiện trên database server của ứng dụng.

##### SQL Injection:
- Là một kỹ thuật cho phép attacker chèn mã SQL vào dữ liệu gửi đến server và được thực hiện trên database server.
- Nguyên nhân:
    - Dữ liệu đầu ra từ user hoặc các nguồn không được kiểm tra hoặc kiểm tra không kĩ.
    - Ứng dựng dùng các câu lệnh SQL động, trong đó dữ liệu được kết nối với mã SQL gốc để tạo câu lệnh SQL hoàn chỉnh.
- Tuỳ mức độ tinh vi, SQL Injection có thể cho phép attacker:

###### Vượt qua các khâu xác thực người dùng:
> Ví dụ form HTML đăng nhập:
> 
> ![image](https://hackmd.io/_uploads/rJziQakU-g.png)
> ![image](https://hackmd.io/_uploads/S1z3XpJIWg.png)
> Phân tích:
> 
> ![image](https://hackmd.io/_uploads/Hkr6may8-g.png)
- Phòng chống/Sửa chữa:
    - Kiểm soát kích thước và định dạng của dữ liệu đầu vào, lọc bỏ các ký tự đặc biệt, từ khoá SQL.
    - Tránh dùng câu truy vấn trực tiếp, nên dùng:
        - Stored Procedure là dạng các lệnh SQL dưới dạng các thủ tục và được lưu trong database:
      
        ![image](https://hackmd.io/_uploads/ryo64T1L-l.png)
            - Storaged Procedure được lưu trong database nên nhanh hơn.
            - Hạn chế tối đa tấn công chèn mã.
        - Dùng các cơ chế truyền tham số, tạo truy vấn của ngôn ngữ.
> - Chỉnh sửa form đăng nhập - Thêm giới hạn kích thước dữ liệu:
> 
> ![image](https://hackmd.io/_uploads/S17U4pJUbe.png)
> - Chỉnh sửa mã asp xử lý đăng nhập trong `test_sql.asp`:
> 
> ![image](https://hackmd.io/_uploads/By_K46yL-g.png)
> ![image](https://hackmd.io/_uploads/HJjcN6k8Zl.png)
> ![image](https://hackmd.io/_uploads/B1Vh4TyUbl.png)
> - Gọi thủ tục `sp_accountLogin` từ mã Assembly:
> 
> ![image](https://hackmd.io/_uploads/HkiBBTy8be.png)

###### Sửa đổi hoặc xoá dữ liệu:
> Ví dụ form HTML tìm kiếm sản phẩm:
> 
> ![image](https://hackmd.io/_uploads/HkKDSaJUbl.png)
> - Mã asp xử lý tìm kiếm trong `file_sql.asp`:
> 
> ![image](https://hackmd.io/_uploads/SkdnSpJ8-e.png)
> - Phân tích:
> 
> ![image](https://hackmd.io/_uploads/Hk56H61UZl.png)
> ![image](https://hackmd.io/_uploads/HJFAHaJUbx.png)

###### Đánh cắp thông tin trong database:
- Lỗi chèn mã SQL có thể cho phép tin tặc đánh cắp dữ liệu nhạy cảm trong database thông qua một số bước:
  - Tìm lỗi chèn mã SQL và thăm dò các thông tin về database: Với phiên bản database server, nhập các câu lệnh lỗi và kiểm tra thông báo lỗi hoặc dùng `@@versions` (MS SQL) hoặc `version()` (MySQL) trong `UNION SELECT`.

  ![image](https://hackmd.io/_uploads/HJUyw6JUWl.png)
  - Trích xuất thông tin về tên các bảng, trường trong database.

  ![image](https://hackmd.io/_uploads/r1Yevak8-g.png)
  ![image](https://hackmd.io/_uploads/ryTbPakLWg.png)
  ![image](https://hackmd.io/_uploads/BkU7vT1Lbg.png)
- Bằng thủ thuật tương tự, tin tặc có thể đánh cắp gần như mọi thông tin trong database.
  - Sử dụng lệnh `UNION SELECT` để ghép các thông tin định trích xuất vào câu lệnh query hiện tại của ứng dụng.
> Ví dụ: Form tìm kiếm sản phẩm có lỗi chèn mã SQL với câu lệnh tìm kiếm

> ![image](https://hackmd.io/_uploads/HkX9I6yUbe.png)

###### Chiếm quyền điều khiển hệ thống:
Khả năng máy chủ database bị chiếm quyền điều khiển xảy ra khi website và database của nó tồn tại:
- Lỗ hổng cho phép tấn công chèn mã SQL.
- Lỗ hổng thiết lập quyền truy nhập - Sử dụng user có quyền quản trị để truy nhập và thao tác dữ liệu website.
- Tin tặc có thể chèn mã để chạy các thủ tục hệ thống cho phép can thiệp vào hệ quản trị database và hệ điều hành.
> MS SQL cung cấp các thủ tục hệ mở rộng:
> 
> ![image](https://hackmd.io/_uploads/ryno_a1IWe.png)
- Tin tặc có thể thực hiện các thao tác nguy hiểm đến database nếu có quyền của admin database hoặc quản trị hệ thống.
> ![image](https://hackmd.io/_uploads/HykyKTJUZg.png)

###### Phòng chống:
- Các biện pháp phòng chống dựa trên kiểm tra và lọc dữ liệu đầu vào.
    - Kiểm tra tất cả dữ liệu đầu vào, đặc biệt dữ liệu nhập từ user và từ các nguồn không tin cậy.
    - Kiểm tra định dạng và kích thước dữ liệu đầu vào.
    - Tạo bộ lọc để lọc bỏ lý tự đặc biệt, các từ khoá của các ngôn ngữ mà attacker có thể dùng:
        - Các ký tự đặc biệt: `*`, `'`, `=`, `--`,...
        - Các từ khoá: `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `DROP`,...
- Các biện pháp phòng chống dựa trên việc dùng thủ tục (stored procedures) trong database:
    - Đưa tất cả câu truy vấn (`SELECT`) và cập nhật, sửa, xoá dữ liệu (`INSERT`, `UPDATE`, `DELETE`) vào thủ tục. Dữ liệu truyền vào thủ tục thông qua tham số thì tách ra khỏi mã.
    - Hạn chế thực hiện các câu lệnh SQL trong thủ tục.
- Cấm hoặc vô hiệu hoá (disable) việc thực hiện các thủ tục hệ thống - Các thủ tục database có sẵn cho phép can thiệp vào hệ quản trị database và hệ điều hành nền.
> Các Extended/System Stored Procedures trong MS SQL như `xp_cmdshell` cho phép chạy lệnh của hệ điều hành.
- Các biện pháp phòng chống dựa trên thiết lập quyền truy nhập user cho phù hợp:
    - Không dùng user có quyền system admin hoặc database owner làm user truy cập dữ liệu.
    - Chia nhóm user, chỉ cấp quyền vừa đủ để truy cập bảng biểu, thực hiện câu truy vấn và chạy các thủ tục.
    - Tốt nhất không cấp quyền thực hiện các câu truy vấn, cập nhật, sửa, xoá trực tiếp dữ liêu. Thủ tục hoá tất cả các câu lệnh và chỉ cấp quyền thực hiện thủ tục.
- Chủ động dùng công cụ rà quét lỗ hổng bảo mật để rà quét tìm các lỗ hổng và khắc phục:
    - Rà quét ứng dụng web/website dùng Acunetix để phát hiện các lỗi chèn mã SQL.
    - Sử dụng SQLmap (Công cụ mã nguồn mở viết bằng Python):
        - Cho phép kiểm tra website tìm lỗi chèn mã SQL.
        - Cho phép khai thác lỗi để điều khiển máy chủ database.
        - Hỗ trợ hầu hết các máy chủ quản trị database hiện nay (MySQL, Oracle, PostfreSQL, Microsoft SQL Server, Microsoft Access, IBM DB2, SQLite, Firebird, Sybase, SAP MaxDB).

### 3. Tấn công từ chối dịch vụ (DoS - Denial of Service Attacks):
- Là dạng tấn công cản trở user hợp pháp truy nhập các tài nguyên hệ thống.
- Hai loại tấn công:
    - Tấn công logic (Logic attacks): Tấn công dựa vào các lỗi phần mềm làm dịch vụ ngừng hoạt động hoặc làm giảm hiệu năng hệ thống. Cần cài đặt các bản cập nhật thường xuyên để phòng chống.
    - Tấn công gây ngập lụt (Flooding attacks): Attacker gửi một lượng lớn requests gây cạn kiệt tài nguyên hệ thống hoặc băng thông đường truyền mạng.
- Các kỹ thuật tấn công:
    - SYN flood
    - Smurf
    - UPD flood
    - HTTP flood
    - Teardrop
    - LandAttack
    - Ping of death
    - ...

#### a) SYN flood:
- Là kỹ thuật gây ngập lụt các gói tin mở kết nối TCP.
> SYN là bit điều khiển của TCP dùng để đồng bộ số trình tự gói.
- Khai thác điểm yểu trong thủ tục bắt tay ba bước khi thiết lập kết nối cho phiên truyền thông TCP/IP.
- Gây cạn kiệt tài nguyên máy chủ:
    - Có thể làm máy chủ ngừng hoạt động.
    - Hoặc không chấp nhận yêu cầu mở kết nối mới.

##### Kịch bản tấn công:
![image](https://hackmd.io/_uploads/Hy9Nf2lLWe.png)
- Attacker gửi một lượng lớn gói tin yêu cầu mở kết nối (`SYN-REQ`) đến máy tính nạn nhân.
- Máy nạn nhân ghi nhận yêu cầu kết nối và dành một chỗ trong bảng lưu kết nối trong bộ nhớ cho mỗi yêu cầu kết nối.
- Máy nạn nhân sau đó gửi gói tin xác nhận kết nối (`SYN-ACK`) đến attacker.
- Do attacker không bao giờ trả lời xác nhận kết nối, máy nạn nhân vẫn phải lưu tất cả các yêu cầu kết nối chưa được xác nhận trong bảng $\rightarrow$ Bảng kết nối đầy và user hợp pháp không thể truy nhập.
- Máy nạn nhân chỉ có thể xoá yêu cầu kết nối chưa được xác nhận khi timed-out.

##### Phân tích:
- Attacker thường dùng IP giả mạo hoặc địa chỉ không có thật là source IP trong gói tin IP nên thông điệp `SYN-ACK` của máy nạn nhân không bao giờ đến đích.
- Attacker cố tình tạo một lượng rất lớn yêu cầu kết nối dở dang để:
    - Các yêu cầu kết nối `SYN-REQ` điền đầy bảng kết nối $\rightarrow$ Máy nạn nhân không thể chấp nhận yêu cầu của những user khác.
    - Làm cạn kiệt tài nguyên bộ nhớ của máy nạn nhân $\rightarrow$ Có thể làm máy nạn nhân ngừng hoạt động.
    - Gây nghẽn đường truyền mạng.

##### Phòng chống:
- Sử dụng kỹ thuật lọc (Filtering): Cần sửa đổi giao thức TCP không cho phép attacker giả mạo địa chỉ.
- Tăng kích thước bảng kết nối (Backlog): Tăng kích thước Backlog lưu các yêu cầu kết nối $\rightarrow$ Tăng khả năng chấp nhận các yêu cầu.
- Giảm thời gian chờ (`SYN-RECEIVED Timer`), các kết nối chưa được xác nhận sẽ bị xoá khi hết thời gian chờ.
- SYN cache: Yêu cầu kết nối chỉ được cấp phát không gian nhớ đầy đủ khi nó được xác nhận.
- Dùng Firewall và Proxies:
    - Có khả năng nhận dạng các địa chỉ IP nguồn là địa chỉ không có thực.
    - Có khả năng tiếp nhận kết nối, chờ đến khi có xác nhận mới chuyển lại cho máy chủ đích.

#### b) Smurf:
Sử dụng kiểu phát quảng bá có định hướng để gây ngập lụt đường truyền mạng của máy nạn nhân.

##### Kịch bản tấn công:
![image](https://hackmd.io/_uploads/By0dN3eLZe.png)
- Attacker gửi một lượng lớn gói tin ICMP (Ping) với địa chỉ nguồn là địa chỉ của máy nạn nhân đến một mạng dùng một địa chỉ quảng bá (IP Broadcast address).
- Các máy trong mạng nhận được thông điệp ICMP sẽ gửi trả lời đến máy có địa chỉ IP là địa chỉ nguồn (máy nạn nhân) trong thông điệp ICMP. Nếu lượng máy trong mạng rất lớn $\rightarrow$ Máy nạn nhân sẽ bị ngập đường truyền.

##### Phòng chống:
- Cấu hình các máy và router không trả lời các yêu cầu ICMP hoặc các yêu cầu phát quảng bá.
- Cấu hình các router không chuyển tiếp yêu cầu gửi đến các địa chỉ quảng bá.
- Dùng tường lửa để lọc các gói tin với địa chỉ giả mạo địa chỉ trong mạng.

#### c) Tấn công DDoS (Distrubuted Denial of Service Attacks):
Là loại tấn công DoS:
- Liên quan đến gây ngập lụt các máy nạn nhân với lượng rất lớn yêu cầu kết nối giả mạng.
- Khác DoS ở phạm vi tấn công:
    - Số lượng máy tham gia tấn công DoS thường tương đối nhỏ, chỉ gồm một số ít máy tại một hoặc một số ít địa điểm.
    - Số lượng máy tham gia tấn công DDoS thường rất lớn, có thể lên đến hàng nghìn hoặc trăm nghìn và đến từ rất nhiều vị trí địa lý khác nhau trên toàn cầu.

##### Kịch bản tấn công:
![image](https://hackmd.io/_uploads/By8ZwngLZg.png)
- Attacker chiếm quyền điều khiển hàng trăm thậm chí hàng nghìn máy tính trên Internet và cài các chương trình tấn công tự động (Automated agents) lên các máy này:
    - Automated agents còn được gọi là các Bots hoặc Zombies.
    - Các máy bị chiếm quyền điều khiển hình thành mạng máy tính ma, gọi là botnet hay zombie network.
- Attacker ra lệnh cho các automated agents đồng loạt tạo các yêu cầu giả mạo gửi đến các máy nạn nhân.
- Lượng yêu cầu giả mạo có thể rất lớn và đến từ rất nhiều nguồn khác nhau nên rất khó đối phó và lần vết để tìm attacker thật sự.

##### Tấn công Reflective DDoS (DDoS phản chiếu hay gián tiếp):
![image](https://hackmd.io/_uploads/BJbTfae8-e.png)
- Là một loại tấn công DDoS với một số điểm khác biệt:
    - Các máy tính do attacker điều khiển (Slaves/Zombies) không trực tiếp tấn công máy nạn nhân.
    - Chúng gửi lượng lớn yêu cầu giả mạo với địa chỉ nguồn là địa chỉ máy nạn nhân đến một ssô lớn các máy khác (Reflectors) trên Internet.
    - Các Reflectors gửi Reply đến máy nạn nhân do địa chỉ của máy nạn nhân được đặt vào địa chỉ nguồn của yêu cầu giả mạo.
    - Nếu các Reflectors có số lượng lớn, số Reply sẽ rất lớn và gây ngập lụt máy nạn nhân.
- Khó lần vết và phòng chống hơn DDoS thông thường do có thể qua nhiều cấp.

### 4. Tấn công giả mạo địa chỉ IP (IP Snoofing):
![image](https://hackmd.io/_uploads/S1bwXaeUbx.png)
- Là dạng tấn công trong đó attacker dùng địa chỉ IP giả, thường để lừa máy nạn nhân để vượt qua các hàng rào kiểm soát an ninh.
- Nếu attacker giả địa chỉ IP là địa chỉ cục bộ của mạng LAN, hắn có thể có nhiều cơ hội đột nhập vào các máy khác trong LAN do chính sách kiểm soát an ninh với các máy trong mạng LAN thường được giảm nhẹ.
- Nếu router hoặc firewall của mạng không được cấu hình để nhận ra IP giả mạo của mạng LAN nội bộ, attacker có thể thực hiện.

![image](https://hackmd.io/_uploads/r1Gumpg8Zg.png)
![image](https://hackmd.io/_uploads/H1GImTxLZx.png)

### 5. Tấn công nghe trộm (Sniffing/Eavesdropping):
Là dạng tấn công sử dụng thiết bị phần cứng hoặc phần mềm, lắng nghe trên card mạng, hub, switch, hoặc router để bắt các gói tin dùng cho phân tích về sau.

![image](https://hackmd.io/_uploads/H1gyETeUbg.png)

### 6. Tấn công kiểu người đứng giữa (Man-in-the-middle):
![image](https://hackmd.io/_uploads/H1joNagLZl.png)
- Lợi dụng quá trình chuyển gói tin đi qua nhiều trạm (hop) thuộc các mạng khác nhau.
- Attacker chặn bắt các thông điệp giữa hai bên tham gia truyền thông, có thể xem, sửa đổi và chuyển thông điệp lại cho bên kia.
- Thường được dùng để đánh cắp thông tin.

![image](https://hackmd.io/_uploads/H16hVpx8bx.png)

### 7. Tấn công bằng bom thư (Mail bombing) và thư rác (Spam emails):
#### 1. Mail bombing:
Là dạng tấn công DoS khi attacker chuyển một lượng lớn email đến nạn nhân:
- Có thể thực hiện được bằng kỹ thuật Social Engineering.
- Hoặc khai thác lỗi trong hệ thống gửi nhận email SMTP.
- Attacker có thể lợi dụng các máy chủ email không được cấu hình tốt để gửi email cho chúng.

#### 2. Spam emails:
- Spams là những email không mong muốn, thường là các emails quảng cáo.
- Spams gây lãng phí tài nguyên tính toán và thời gian của user (phải lọc, xoá).
- Spams cũng có thể dùng để chuyển các phần mềm độc hại.

### 8. Tấn công dùng Backdoors:
- Backdoors thường được các lập trình viên tạo ra dùng để gỡ rối và test chương trình.
- Backdoors thường cho phép truy nhập trực tiếp vào hệ thống mà không qua các thủ tục kiểm tra an ninh thông thường.
- Khi backdoors được lập trình viên tạo ra để truy nhập hệ thống bất hợp pháp, nó trở thành một mối đe doạ đến an ninh và hệ thống.
- Rất khó để phát hiện ra backdoors vì nó thường được thiết kế và cài đặt khéo léo, chỉ được kích hoạt trong một ngữ cảnh nào đó.

### 9. Tấn công kiểu Social Engineering:
Là dạng tấn công dùng các kỹ thuật xã hội nhằm thuyết phục user tiết lộ thông tin truy cập hoặc các thông tin có giá trị cho attacker:
- Attacker có thể giả làm người có vị trí cao hơn so với nạn nhân để có được sự tin tưởng.
- Attacker có thể mạo danh là người được uỷ quyền của người có thẩm quyền để yêu cầu các nhân viên tiết lộ thông tin về cá nhân/tổ chức.
- Attacker có thể lập trang web giả để đánh lừa user cung cấp các thông tin cá nhân và thông tin nhạy cảm.
> Trò lừa đảo Nigeria 4-1-9 lợi dụng sự ngây thơ và lòng tham của nhiều người:
> - Kẻ lừa đảo gửi thư tay hoặc email đến nhiều người nhận, mô tả về việc có một khoản tiền lớn (thừa kế, lợi tức,...) cần chuyển ra nước ngoài, nhờ người nhận giúp đỡ để hoàn thành giao dịch. Khoản tiền có thể lên đến hàng chục hoặc trăm triệu USD. Attacker hứa sẽ trả cho người nhận một phần tỉ lệ số tiền.
> - Nếu người nhận có phản hổi và đồng ý tham gia, attacker sẽ gửi tiếp thư/email khác, yêu cầu chuyển cho hắn một khoản phí giao dịch.
> - Nếu người nhận gửi tiền cho attacker, người đó sẽ mất tiền.

#### a) Phishing:
Là một dạng của tấn công Social Engineering, lừa user để lấy thông tin cá nhân, thông tin nhạy cảm.
- Attacker có thể giả mạo trang web của các tổ chức.
- Chúng gửi email cho người dùng (địa chỉ email thu thập trên mạng), yêu cầu xác thực thông tin.
- Nếu user làm theo thì sẽ cung cấp các thông tin cho attacker.
>![image](https://hackmd.io/_uploads/BJzhv6e8Zl.png)

#### b) Pharming:
Là kiểu tấn công vào trình duyệt user:
- User gõ địa chỉ một website, trình duyệt lại yêu cầu một website độc hại khác.
- Attacker thường sử dụng virus hoặc các phần mềm độc hại cài vào hệ thống để điều khiển trình duyệt của user.
- Attacker cũng có thể tấn công vào hệ thống DNS để thay đổi kết quả truy vấn: thay địa chỉ IP của website hợp pháp thành IP của website độc hại.
> ![image](https://hackmd.io/_uploads/SkKSupgUZe.png)
> ![image](https://hackmd.io/_uploads/rJOLuTlIZg.png)

## IV. Các dạng phần mềm độc hại:
![image](https://hackmd.io/_uploads/H1cwuag8-x.png)

### 1. Logic bombs:
- Thường được "nhúng" vào các chương trình bình thường và thường hẹn giờ để "phát nổ" trong một số điều kiện cụ thể:
    - Sự xuất hiện hoặc biến mất của các files cụ thể.
    - Một thời gian nào đó.
    - ...
- Khi "phát nổ" có thể xoá dữ liệu, files, tắt hệ thống,...
> Logic bomb do Tim Lloyd cài lại đã "phát nổ" tại công ty Omega Engineering vào 30/07/1996, 20 ngày sau khi Tim Lloyd bị sa thải. Logic bomb này đã xoá sạch các bản thiết kế và các chương trình, gây thiệt hại mười triệu USD. Tim Lloyd bị phạt hai triệu đô và 41 tháng tù.

### 2. Trojan horses:
- Lấy tên theo tích "Con ngựa thành Troy".
- Chứa mã độc, thường giả danh chương trình có ích nhằm lừa user kích hoạt chúng.
- Thường được dùng để thực thi gián tiếp các tác vụ mà tác giả của chúng không thể thực hiện trực tiếp do không có quyền truy cập.
> Trong một hệ thống nhiều users, một user có thể tạo ra một trojan đội lốt một chương trình hữu ích đặt ở thư mục chung. Khi trojan này được thực thi bởi một user khác, nó sẽ cho phép tất cả users truy nhập vào các files của user đó.

### 3. Zombie:
![image](https://hackmd.io/_uploads/S1RucTgLWx.png)
![image](https://hackmd.io/_uploads/SyKgoTe8Wl.png)
- Còn gọi là bot hoặc automated agent, là một chương trình được thiết kế để giành quyền kiểm soát một máy tính có kết nối Internet và dùng máy tính bị kiểm soát để tấn công các hệ thống khác.
- Các zombies thường được dùng để gửi thư rác và tấn công DDoS các máy chủ, website lớn.
- Rất khó để lần vết và phát hiện ra tác giả tạo ra, điều khiển zombies.

### 4. Viruses:
- Là chương trình có thể "nhiễm" vào các chương trình khác bằng cách sửa đổi các chương trình này.
- Nếu các chương trình đã bị sửa đổi chứa virus được kích hoạt thì virus sẽ tiếp tục "lây nhiễm" sang các chương trình khác.
- Giống như virus sinh học, virus máy tính cũng có khả năng tự nhân bản, tự lây nhiễm sang các chương trình khác mà nó tiếp xúc.
- Có nhiều con đường lây nhiễm: sao chép file, gọi các ứng dụng và dịch vụ qua mạng, email,...
- Virus có thể thực hiện được mọi việc mà một chương trình thông thường có thể thực hiện. Khi đã lây nhiễm vào một chương trình, virus tự động được thực hiện khi chương trình này chạy.

#### Bốn giai đoạn vòng đời:
- Giai đoạn "nằm im": Virus trong giai đoạn không được kích hoạt, có thể được kích hoạt nhờ sự kiện nào đó.
- Giai đoạn phát tán: Virus cài một bản sao của nó vào các chương trình khác.
- Giai đoạn kích hoạt: Được kích hoạt để thực thi các tác vụ đã thiết lập được định sẵn. Virus cũng thường được kích hoạt dựa trên sự kiện nào đó.
- Giai đoạn thực hiện: Thực thi các tác vụ, một số viruses có thể vô hại nhưng một số có thể xoá dữ liệu, chương trình,...
#### Các loại virus:
- Boot virus: Virus lây nhiễm vào cung khởi động của đĩa.
- File virus: Virus lây nhiễm vào các files chương trình hoặc tài liệu. Cơ chế chèn mã:
    - Virus có thể chèn mã của nó vào đầu hoặc cuối chương trình lây nhiễm.
    - Khi chương trình nhiễm virus được thực hiện, mã virus được thực hiện trước, sau đó mã chương trình mới được thực hiện.
  
    ![image](https://hackmd.io/_uploads/ByOQpplLWe.png)
- Macro virus:
    - Virus lây nhiễm vào các file tài liệu của bộ chương trình Microsoft Office và ứng dụng office khác.
    - Hoạt động được nhờ:
        - Tính năng cho phép tạo và thực hiện các đoạn mã macro trong các tài liệu của bộ ứng dụng Microsoft Office.
        - Các đoạn mã macro thường được dùng để tự động hoá một số việc và được viết bằng ngôn ngữ Visual Basic for Applications (VBA).
    - Các ứng dụng văn phòng khác như Open Office không hỗ trợ VBA không bị ảnh hưởng bởi macro virus.
    - Thường lây nhiễm vào các files định dạng chuẩn và từ đó lây nhiễm vào tất cả các files tài liệu được mở.
    - Cũng có thể được tự động kích hoạt nhờ các auto-executed macros: AutoExecute, Automacro và Command macro.
- Email virus: Virus lây nhiễm thông qua việc gửi, nhận và xem email.
    - Lây nhiễm bằng cách tự động gửi một bản copy của nó như một file đính kèm đến tất cả các địa chỉ email trong sổ địa chỉ của user trên máy bị lây nhiễm.
    - Nếu user mở email hoặc file đính kèm, virus được kích hoạt.
    - Có thể lây nhiễm rất nhanh chóng, lan tràn trên khắp thế giứi trong thời gian ngắn.
### 5. Worms:
- Có khả năng tự lây nhiễm từ máy này sang máy khác mà không cần sự trợ giúp của user (khác email viruses).
- Khi lây nhiễm vào một máy, nó dùng máy này làm bàn đạp để tiếp tục tấn công máy khác.
- Dùng kết nối mạng để lây lan từ máy này sang máy khác.
- Hoạt động tương tự virus.
- Mô hình lây lan:

![image](https://hackmd.io/_uploads/rysRR6gIZx.png)
- Các phương pháp lây lan:
    - Qua thư điện tử: Dùng email để gửi bản copy đến các máy khác.
    - Thông qua khả năng thực thi từ xa: Thực thi một bản copy của nó lên một máy khác nhờ lợi dụng các lỗ hổng an ninh của hệ điều hành, các dịch vụ hoặc phần mềm ứng dụng.
    - Thông qua khả năng đăng nhập từ xa: Đăng nhập vào hệ thống ở xa như một user và dùng lệnh để copy bản thân từ máy này sang máy khác.
> Code Red (07/2001):
> - Lợi dụng một lỗ hổng an ninh trong MS IIS để lây lan (lỗi tràn bộ đêm khi xử lý các file `.ida` của IIS).
> - Quét các địa chỉ IP ngẫu nhiên để tìm các hệ thống có lỗi.
> - Lây nhiễm vào 360000 máy chủ trong vòng 14 giờ.

### 6. Phòng chống:
- Ngăn chặn viruses lây nhiễm vào hệ thống:
    - Luôn cập nhật hệ thống để hạn chế các lỗi phần mềm.
    - Dùng các biện pháp kiểm soát truy nhập.
- Khi phát hiện hệ thống đã nhiễm virus:
    - Phát hiện virus.
    - Nhận dạng virus.
    - Loại bỏ virus.
- Một số phần mềm diệt virus và phần mềm độc hại:
    - Microsoft Security Enssentials
    - Sematec Norton Antivirus
    - Kaspersky Antivirus
    - BitDefender Antivirus
    - AVG Antivirus
    - McAfee VirusScan
    - Trend Micro Antivirus
    - F-secure
    - BKAV
    - ...
