## I. Tổng quan:
### 1. Các thành phần của hệ thống máy tính:
![image](https://hackmd.io/_uploads/ByN2GQWH-x.png)
#### Hệ thống phần cứng:
- CPU, ROM, RAM, BUS,...
- Các giao diện ghép nối và các thiết bị ngoại vi.

#### Hệ thống phần mềm:
##### Hệ điều hành:
- Nhân hệ điều hành, các trình điều khiển thiết bị.
- Các trình cung cấp dịch vụ, tiện ích.

##### Các phần mềm ứng dụng:
- Các dịch vụ (web server, database, DNS,...).
- Trình duyệt web, các ứng dụng giao tiếp,...
- Các bộ ứng dụng văn phòng, lập trình.

### 2. Khái niệm điểm yếu hệ thống và các lỗ hổng bảo mật:
#### Điểm yếu hệ thống (System weaknesss):
Là các lỗi hay khiếm khuyết (thiết kế, cài đặt, phần cứng, phần mềm) tồn tại trong hệ thống:
- Có điểm yếu đã biết và đã được khắc phục.
- Có điểm yếu đã biết và chưa được khắc phục.
- Có điểm yếu chưa biết/chưa được phát hiện.

#### Lỗ hổng bảo mật (Security vulnerability):
- Là một điểm yếu trong hệ thống cho phép attacker khai thác gây tổn hại đến các thuộc tính an ninh, an toàn của hệ thống:
    - Toàn vẹn (integrity).
    - Bí mật (confidentiality).
    - Sẵn sàng (availability).
- Mức độ nghiêm trọng của lỗ hổng bảo mật:

##### Theo Microsoft:
- Nguy hiểm (Critical)
- Quan trọng (Important)
- Trung bình (Moderate)
- Thấp (Low)

##### Theo một số tổ chức khác:
- Cao (High)
- Trung bình (Medium)
- Thấp (Low)

#### Mô hình quan hệ giữa các đối tượng và vai trò trong hệ thống:
![image](https://hackmd.io/_uploads/ry6xLm-SWx.png)
![image](https://hackmd.io/_uploads/SJab8XbHZl.png)

## II. Các dạng lỗ hổng trong hệ điều hành và phần mềm ứng dụng:
Các dạng lỗ hổng thường gặp:

### Lỗi tràn bộ nhớ đệm (Buffer Overflows):
- Xảy ra khi một số ứng dụng cố gắng ghi dữ liệu vượt khỏi phạm vi bộ đệm (giới hạn đầu cuối của bộ đệm).
- Có thể khiến ứng dụng ngừng hoạt động, gây mất dữ liệu hoặc thậm chí giúp attacker kiểm soát hệ thống.
- Là lỗi trong khâu lập trình phần mềm và chiếm tỷ lệ lớn trong các lỗi gây lỗ hổng bảo mật.
- Không phải tất cả các lỗi tràn bộ đệm có thể bị khai thác bởi attacker.
- Các vùng chứa bộ nhớ đệm của ứng dụng:
    - Ngăn xếp (Stack): Vùng nhớ lưu các tham số gọi hàm, thủ tục, phương thức và dữ liệu cục bộ của ứng dụng.
    - Vùng nhớ cấp phát động (Heap): Là vùng nhớ chung lưu dữ liệu cho ứng dụng.
> Bài trình bày *Smashing the Stack* của Mark Shaneck (2003) giải thích cơ chế lỗi tràn bộ đệm trên bộ nhớ Stack và khả năng khai thác lỗ hổng:
> - Cơ chế hoạt động của Stack.
> - Minh hoạ lỗi tràn bộ đệm trong Stack.
> - Giải thích khả năng khai thác lỗi.
> - Giải thích cơ chế hoạt động của SQL Slammer và MS Blast - Khai thác lỗi tràn bộ đệm.
- Các biện pháp phòng chống:
    - Kiểm tra mã nguồn thủ công để tìm và khắc phục các điểm có khả năng xảy ra lỗi tràn bộ đệm.
    - Sử dụng các công cụ phân tích mã tự động tìm các điểm có khả năng xảy ra lỗi tràn bộ đệm.
    - Đặt cơ chế không cho phép thực thi mã trong Stack (DEP - Data Execution Prevention).
    - Sử dụng các cơ chế bảo vệ Stack:
        - Thêm một số ngẫu nhiên (canary) phía trước địa chỉ trở về.
        - Kiểm tra số này trước khi trở về chương trình gọi để xác định khả năng bị thay đổi địa chỉ trở về.
    - Sử dụng các ngôn ngữ hay công cụ lập trình không gân tràn (trong trường hợp có thể):
        - Ngôn ngữ không gây tràn: Java, .Net
        - Các thư viện an toàn.

### Không kiểm tra đầu vào (Unvalidated Input):
- Các dữ liệu đầu vào (input data) cần được kiểm tra để đảm bảo đạt các yêu cầu về định dạng và kích thước.
- Các dạng dữ liệu nhập điển hình cần kiểm tra:
    - Các trường dữ liệu text.
    - Các lệnh được truyền qua URL để kích hoạt chương trình.
    - Các file âm thanh, hình ảnh hoặc đồ hoạ do user hoặc các tiến trình khác cung cấp.
    - Các đối số đầu vào trong command.
    - Các dữ liệu từ mạng hoặc các nguồn không tin cậy.
- Attacker có thể kiểm tra các dữ liệu đầu vào và thử tất cả các khả năng có thể để khai thác.
> - Trang web bị lỗi do không kiểm tra dữ liệu đầu vào từ URL:
> 
> ![image](https://hackmd.io/_uploads/HJxGo7Wr-e.png)
> - Chèn mã độc SQL vào trường text:
> 
> ![image](https://hackmd.io/_uploads/r1AmomWB-l.png)
> - Chèn mã SQL để đăng nhập mà không cần account và password:
> 
> ![image](https://hackmd.io/_uploads/Bkwvi7WSWe.png)
- Các biện pháp phòng chống:
    - Kiểm tra tất cả dữ liệu đầu vào, đặc biệt dữ liệu nhập từ user và từ các nguồn không tin cậy.
    - Kiểm tra định dạng và kích thước dữ liệu đầu vào.
    - Kiểm tra sự hợp lý của nội dung dữ liệu.
    - Tạo các filters để lọc bỏ các ký tự đặc biệt và các từ khoá của ngôn ngữ trong các trường hợp cần thiết mà attacker có thể dùng:
        - Các ký tự đặc biệt: `*`, `'`, `=`, `--`,...
        - Các từ khoá: `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `DROP`,...

### Các vấn đề với điều khiển truy cập (Access - control):
- Điều khiển truy nhập liên quan đến việc điều khiển **ai** (chủ thể) được truy nhập đến **cái gì** (đối tượng).
- Điều khiển truy nhập có thể được thiết lập trong hệ điều hành hoặc mỗi ứng dụng, thường gồm hai bước:
    - Xác thực (Authentication): Xác thực thông tin nhận dạng của chủ thể.
    - Trao quyền (Authorization): Cấp quyền truy nhập cho chủ thể sau khi thông tin nhận dạng được xác thực.
- Các chủ thể được cấp quyền truy nhập vào hệ thống theo các cấp độ khác nhau dựa trên chính sách an ninh của tổ chức.
- Nếu kiểm soát truy nhập bị lỗi, một user bình thường có thể đoạt quyền của admin và toàn quyền truy nhập vào hệ thống.
- Một attacker có thể lợi dụng lỗ hổng bảo mật của hệ thống kiểm soát truy nhập để truy nhập vào các file trong hệ thống.
- Một ứng dụng chạy trên user quản trị (root hoặc domain) có toàn quyền truy nhập vào hệ thống (Nếu một attacker chiếm được quyền điều khiển chương trình sẽ có toàn quyền truy nhập).
- Cách phòng chống:
    - Không dùng user quản trị để chạy các chương trình ứng dụng.
    - Luôn chạy các chương trình ứng dụng với quyền tối thiểu, vừa đủ để thực thi các tác vụ.
    - Kiểm soát chặt ché user, xoá bỏ hoặc cấm truy nhập với những người dùng ngầm định kiểu `everyone`.
    - Thực thi chính sách mật khẩu an toàn.
    - Cấp quyền vừa đủ cho user thực thi nhiệm vụ.

### Các điểm yếu trong xác thực, trao quyền hoặc các hệ mật mã:
- Xác thực:
    - Mật khẩu được lưu dưới dạng plaintext $\rightarrow$ Nguy cơ lộ rất cao trong quá trình truyền thông tin xác thực.
    - Sử dụng mật khẩu đơn giản, dễ đoán hoặc dùng mật khẩu trong thời gian dài.
    - Sử dụng cơ chế xác thực không đủ mạnh, ví dụ các cơ chế xác thực của giao thức HTTP.
- Trao quyền: Cơ chế thực hiện trao quyền không đủ mạnh, dễ bị vượt qua.
> Một trang web chỉ thực hiện ẩn các links đến các trang web mà user không được truy nhập mà không thực sự kiểm tra quyền truy nhập trên từng trang. Nếu user tự gõ URL của trang thì vẫn có thể truy nhập.
- Mật mã:
    - Sử dụng giải thuật mã hoá/giải mã, hàm băm yếu, lạc hậu hoặc có lỗ hổng (DES, MD4, MD5,...).
    - Sử dụng mã hoá/giải mã yếu:
        - Khoá có chiều dài ngắn.
        - Khoá dễ đoán.
    - Các vấn đề trao đổi khoá bí mật.
    - Các vấn đề xác thực người gửi/nhận.
    - Chi phí tính toán lớn (đặc biệt với các hệ mã hoá công khai).

### Các lỗ hổng bảo mật khác:
- Các thao tác không an toàn với files:
    - Thực hiện đọc/ghi file lưu ở những nơi mà các user khác cũng có thể ghi file đó.
    - Không kiểm tra chính xác loại file, định danh thiết bị, các links hoặc các thuộc tính khác của file trước khi dùng.
    - Không kiểm tra mã trả về sau mỗi thao tác với file.
    - Giả thiết một file có đường dẫn cục bộ là file cục bộ và bỏ qua các thủ tục kiểm tra: File ở xa có thể được ánh xạ vào hệ thống file cục bộ $\rightarrow$ Có đường dẫn cục bộ.
- Các điều kiện đua tranh (Race conditions):
    - Một điều kiện đua tranh tồn tại khi có sự thay đổi trật tự của hai hay nhiều sự kiện gây ra sự thay đổi hành vi của hệ thống.
    - Đây là dạng lỗi chương trình chỉ có thể thực hiện đúng chức năng nếu các sự kiện xảy ra theo đúng trật tự.
    - Attacker có thể lợi dụng khoảng thời gian giữa hai sự kiện để chèn mã độc, đổi tên file hoặc can thiệp vào quá trình hoạt động bình thường của hệ thống.
> Ví dụ:
> - Các file tạm thời (temporary files) thường được lưu ở một thư mục chung quản lý bởi hệ điều hành. Tiến trình của nhiều user có thể đọc/ghi file tạm thời.
> Nếu một tiến trình tạo các cặp khoá bí mật và công khai rồi lưu chúng vào một file tạm thời và sau đó đọc lại để lưu vào database.
> - Attacker có thể tạo một race condition trong khoảng thời gian tiến trình chuyển từ ghi sang đọc các cặp khoá:
>    - Thay file tạm của tiến trình bằng file chứa khoá của hắn $\rightarrow$ Tiến trình sẽ đọc và lưu khoá của attacker $\rightarrow$ Mọi thông điệp mã hoá sử dụng khoá trên có thể được giải mã.
>    - Đọc file tạm của tiến trình để đánh cắp các cặp khoá.

## III. Quản lý, khắc phục các lỗ hổng bảo mật và tăng cường khả năng đề kháng cho hệ thống:
### Nguyên tắc:
Cân bằng giữa An toàn (Secure) - Hữu dụng (Usable) - Rẻ (Cheap):

![image](https://hackmd.io/_uploads/B1PlQ4WHbe.png)

### Một số biện pháp cụ thể:
- Thường xuyên cập nhật thông tin về các điểm yếu, lỗ hổng bảo mật từ các trang web chính thức:
    - [CVE: Common Vulnerabilities and Exposures](https://www.cve.org/)
    - [CVE Details](https://www.cvedetails.com/)
    - [National Vulnerability Database](https://nvd.nist.gov/)
    - [Vulnerability | OWASP Foundation](https://owasp.org/www-community/vulnerabilities/)
- Định kỳ cập nhật các bản vá, nâng cấp hệ điều hành và các phần mềm ứng dụng:
    - Sử dụng các hệ thống quản lý bản vá và tự động cập nhật định kỳ:
        - Microsoft Windows Updates
        - Tiện ích Update trên Linux
        - Tính năng tự động Update của các ứng dụng (Google Update service,...)
        - ...
    - Với các lỗ hổng nghiêm trọng, cần cập nhật tức thời.
- Một số biện pháp cụ thể:
    - Cần có chính sách quản trị user, mật khẩu và quyền truy nhập chặt chẽ ở mức hệ điều hành và mức ứng dụng:
        - User chỉ được cấp quyền truy nhập vừa đủ để thực hiện công việc được giao.
        - Nếu được cấp nhiều quyền hơn mức cần thiết thì gây ra lạm dụng.
    - Sử dụng các biện pháp phòng chống phòng vệ ở lớp ngoài như tương lửa, proxies:
        - Chặn các dịch vụ/cổng không thực sự cần thiết.
        - Ghi logs các hoạt động truy nhập mạng.
    - Sử dụng các phần mềm rà quét lỗ hổng, rà quét các phần mềm độc hại: Có thể giảm thiểu nguy cơ bị lợi dụng, khai thác lỗ hổng bảo mật.

## IV. Giới thiệu một số công cụ rà quét lỗ hổng bảo mật:
### Công cụ quét cổng dịch vụ:
- Nmap
- Angry IP Scanner
- SuperScan

### Công cụ rà quét lỗ hổng bảo mật hệ thống:
- Microsoft Baseline Security Analyser
- Nessus Vulnerability Scanner

### Công cụ rà quét lỗ hổng ứng dụng web:
- Acunetix Web Vulnerability Scanner
- IBM AppScan
- Beyond Security AVDS
- SQLMap
