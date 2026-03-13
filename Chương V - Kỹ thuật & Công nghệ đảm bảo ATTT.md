## I. Điều khiển truy nhập:
### 1. Khái niệm điều khiển truy nhập:
- Là quá trình mà trong đó user được *nhận dạng* và *trao quyền* truy nhập đến các thông tin, hệ thống và tài nguyên.
- Một hệ thống điều khiển truy nhập có thể được cấu thành từ ba dịch vụ:
    - **Xác thực (Authentication):** Quá trình xác minh tính chân thực của các thông tin nhận dạng mà user cung cấp.
    - **Trao quyền (Authorization):** Trao quyền xác thực các tài nguyên mà user được phép truy nhập sau khi user đã được xác thực.
    - **Quản trị (Administration):** Cung cấp khả năng thêm, bớt và sửa đổi các thông tin tài khoản user cũng như quyền truy nhập của user.
- Trong ba dịch vụ trên, hai dịch vụ là thiết yếu của một hệ thống điều khiển truy nhập là xác thực và trao quyền.
- Mục đích chính của điều khiển truy nhập là để đảm bảo:
    - **Tính bí mật (Confidentiality):** Đảm bảo chỉ những ai có thẩm quyền mới có thể truy nhập vào dữ liệu hệ thống.
    - **Tính toàn vẹn (Integrity):** Đảm bảo dữ liệu không bị sửa đổi bởi các bên không đủ thẩm quyền.
    - **Tính sẵn dùng (Availability):** Đảm bảo tính sẵn sàng (đáp ứng nhanh/kịp thời) của dịch vụ cung cấp cho user thực sự.

### 2. Các biện pháp điều khiển truy nhập:
#### a) Điều khiển truy nhập tuỳ chọn (Discretionaru Access Control - DAC):
- Được định nghĩa là các cơ chế hạn chế truy nhập đến các đối tượng dựa trên thông tin nhận dạng của các chủ thể và/hoặc nhóm của các chủ thể.
- Thông tin nhận dạng có thể gồm:
    - Bạn là ai? (CCCD, vân tay,...)
    - Những gì bạn biết (Tên truy nhập, mật khẩu,...)
    - Bạn có gì? (ATM,...)
- Cho phép user có thể cấp hoặc huỷ quyền truy nhập cho các user khác đến các đối tượng thuộc quyền điều khiển của họ.
- Chủ sở hữu của các đối tượng (Owner of Objects) là user có toàn quyền điều khiển các đối tượng này.
> Ví dụ: Với DAC:
> - User được cấp một thư mục riêng và là chủ sở hữu của thư mục này.
> - User có quyền tạo, sửa đổi hoặc xoá các files trong thư mục của riêng mình (Home Directory).
> - Họ cũng có khả năng trao hoặc huỷ quyền truy nhập vào các files của mình cho các user khác.
- Hai kỹ thuật được sử dụng phổ biết để cài đặt DAC:

##### Ma trận điều khiển truy nhập (Access Control Matrix - ACM):
Là phương pháp mô tả điều khiển truy nhập thông qua một ma trận hai chiều gồm chủ thể (Subject), đối tượng (Object) và các quyền truy nhập:
- Đối tượng/Khách thể (Objects) là các thực thể cần bảo vệ, có thể là các files, tiến trình (processes).
- Chủ thể (Subjects) là users, tiến trình tác động lên objects.
- Quyền truy nhập là hành động mà subjects thực hiện trên objects.

> ![image](https://hackmd.io/_uploads/Bkc-munt-e.png)
> - Các chủ thể: S1, S2, S3
> - Các đối tượng: O1, O2, O3
> - Các quyền: `r` (read), `w` (write), `x` (execute), `o` (own)

##### Danh sách điều khiển truy nhập (Access Control List - ACL):
- Là danh sách các quyền truy nhập của một chủ thể đối với một đối tượng:
    - Một ACL chỉ ra các users hoặc tiến trình được truy nhập vào đối tượng nào đó và các thao tác cụ thể (quyền) được thực hiện trên đối tượng đó.
    - Một bản ghi điển hình của ACL có dạng `(subject, operation)`.
    > Ví dụ: Bản ghi `(Alice, write)` của một file có nghĩa là Alice có quyền ghi vào file đó.
    - Khi chủ thể yêu cầu truy nhập, hệ điều hành sẽ kiểm tra ACL xem yêu cầu đó có được phép hay không.
    - ACL có thể được áp dụng cho một hoặc một nhóm đối tượng.
- Dùng ACL để quản lý việc truy nhập file:

![image](https://hackmd.io/_uploads/HyuyLu3t-e.png)

#### b) Điều khiển truy nhập bắt buộc (Mandatory Access Control - MAC):
- Là các cơ chế hạn chế truy nhập đến các đối tượng dựa trên:
    - Tính nhạy cảm (Sensitivity) của thông tin (thường được gán nhã) chứa trong các đối tượng.
    - Sự trao quyền chính thức (Formal Authorization) cho các chủ thể truy nhập các thông tin nhạy cảm này.
- Các mức nhạy cảm của thông tin:
    - **Tối mật (Top Secret - T):** Được áp dụng với thông tin mà nếu bị lộ có thể dẫn đến những thiệt hại trầm trọng đối với an ninh quốc gia.
    - **Tuyệt mật (Secret - S):** Được áp dụng với thông tin mà nếu bị lộ có thể dẫn đến một loạt thiệt hại đối với an ninh quốc gia.
    - **Mật (Confidential - C):** Được áp dụng với thông tin mà nếu bị lộ có thể dẫn đến thiệt hại đối với an ninh quốc gia.
    - **Không phân loại (Unclassified - U):** Những thông tin không gây thiệt hại đối với an ninh quốc gia nếu bị tiết lộ.
- MAC không cho phép user tạo ra các đối tượng (thông tin/ tài nguyên) có toàn quyền truy nhập các đối tượng này.
- Quyền truy nhập đến các đối tượng (thông tin/tài nguyên) do admin hệ thống định ra trước trên cơ sở chính sách an toàn thông tin của tổ chức đó.
- MAC thường được dùng phổ biến trong các cơ quan an ninh, quân đội và ngân hàng.
> Ví dụ: Một tài liệu được tạo ra và được đóng dấu "Mật":
> - Chỉ những ai có trách nhiệm trong tổ chức mới được quyền xem và phổ biến cho người khác.
> - Tác giả của tài liệu không được quyền phổ biến đến người khác.
- Mô hình điều khiển truy nhập Bell-LaPadula:

![image](https://hackmd.io/_uploads/rJ8oB5ptWx.png)
    - Là mô hình bảo mật đa cấp thường được dùng trong quân sự, nhưng cũng có thể áp dụng cho các lĩnh vực khác.
    - Trong quân sự, các tài liệu được gán một mức độ bảo mật, chẳng hạn như không phân loại, mật, bí mật và tối mật. User cũng được ấn định các cấp độ bảo mật tương ứng, tuỳ thuộc vào những tài liệu họ được phép xem.
    > - Một vị tướng quân đội có thể được phép xem tất cả tài liệu, trong khi một trung uý có thể bị hạn chế chỉ được xem các tài liệu mật và thấp hơn.
    > - Một tiến trình chạy nhân danh một user có được mức độ bảo mật của user đó.
    - Nguyên tắc bảo mật tài nguyên:
        - Nguyên tắc đọc xuống: Một user ở mức độ bảo mật $k$ chỉ có có thể đọc các đối tượng ở cùng mức bảo mật hoặc thấp hơn.
        > Ví dụ: Một vị tướng có thể đọc các tài liệu của một trung uý nhưng một trung uý không thể đọc tài liệu của vị tướng đó.
        - Nguyên tắc ghi tên: Một user ở mức độ bảo mật $k$ chỉ có thể ghi các đối tượng ở cùng mức bảo mật hoặc cao hơn.
        > Ví dụ: Một trung uý có thể nối thêm tin nhắn vào hộp thư của chung về tất cả mọi thứ ông biết, nhưng một vị tướng không thể ghi thêm một tin nhắn vào hộp thư của trung uý với tất cả mọi thứ ông ấy biết vì vị tướng đó có thể đã nhìn thấy tài liệu có một mức độ bảo mật cao mà không thể được tiết lộ cho một trung uý.

#### c) Điều khiển truy nhập dựa trên vai trò (Role-Based Access Control - RBAC):
- Điều khiển truy nhập dựa trên vai trò cho phép user truy nhập vào thông tin và hệ thống dựa trên vai trò (role) của họ trong công ty/tổ chức đó.
- Điều khiển truy nhập dựa trên vai trò có thể được áp dụng cho một nhóm users hoặc từng user riêng lẻ.
- Quyền truy nhập được tập hợp thành nhóm "vai trò" với các mức quyền truy nhập khác nhau.
> Ví dụ: Một trường học chia user thành các nhóm gán sẵn quyền truy nhập vào các phần trong hệ thống.
> - Nhóm Quản lý được quyền truy nhập vào tất cả các thông tin trong hệ thống.
> - Nhóm Giáo viên được truy nhập vào database các môn học, bài báo khoa học, cập nhật điểm các lớp phụ trách.
> - Nhóm Sinh viên chỉ được quyền xem nội dung các môn học, tải tài liệu học tập và xem điểm của mình.
- Liên kết giữa user và vai trò: User được cấp "thẻ thành viên" của các nhóm "vai trò" trên cơ sở năng lực và vai trò, cũng như trách nhiệm của họ trong một tổ chức.
- Trong nhóm "vai trò", user được cấp vừa đủ quyền để thực hiện các thao tác cần thiết cho công việc được giao.
- Liên kết giữa user và vai trò có thể được tạo lập và huỷ bỏ dễ dàng.
- Quản lý phân cấp vai trò: Các vai trò được tổ chức thành một cây theo mô hình phân cấp tự nhiên của các công ty/tổ chức.
- Một mô hình RBAC đơn giản:

![image](https://hackmd.io/_uploads/Hkj7F9TtZx.png)

#### d) Điều khiển truy nhập dựa trên luật (Rule-Based Access Control):
- Điều khiển truy nhập dựa trên luật cho phép user truy nhập vào hệ thống và thông tin dựa trên các rules đã được định nghĩa trước.
- Các rules có thể được thiết lập để hệ thống cho phép truy nhập đến các tài nguyên của mình cho user thuộc một tên miền, mạng hay một dải địa chỉ IP.
> Firewalls/Proxies là ví dụ điển hình về điều khiển truy nhập dựa trên rules.
- Các hệ thống này dùng một tập các rules để điều khiển truy nhập, các thông tin dùng trong luật có thể gồm:
    - Địa chỉ IP nguồn và đích của các gói tin.
    - Phần mở rộng các files để lọc các mã độc hại.
    - Địa chỉ IP hoặc các tên miền để lọc/chặn các website bị cấm.
    - Tập các từ khoá để lọc nội dung bị cấm.

### 3. Một số công nghệ điều khiển truy nhập:
#### a) Điều khiển truy nhập dựa trên mật khẩu (Password):
- Thông thường mỗi user được cấp một tài khoản để truy nhập vào hệ thống. Để truy nhập tài khoản cần có:
    - Tên người dùng, email, số điện thoại,...
    - Mật khẩu:
        - Có thể ở dạng nguyên bản (Plaintext).
        - Có thể ở dạng mã hoá (Encrypted text). Các thuật toán thường dùng để mã hoá mật khẩu: MD4, MD5, SHA1, SHA256,...
        - Có thể được dùng nhiều lần hoặc một lần (OTP - One time password).
- Tính bảo mật của kỹ thuật này dựa trên:
    - Độ khó đoán của mật khẩu:
        - Dùng nhiều loại ký tự: Chữ thường, hoa, chữ số, ký tự đặc biệt.
        - Độ dài của mật khẩu: Dài ít nhất tám ký tự.
    - Tuổi thọ của mật khẩu:
        - Mật khẩu không hết hạn.
        - Mật khẩu có thời hạn sống.
        - Mật khẩu dùng một lần (OTP):
            - Được sinh ra và chỉ được dùng một lần cho một phiên làm việc hoặc một giao dịch.
            - Thường được sinh ngẫu nhiên.
            - Chuyển giao OTP:
                - In ra giấu một danh sách mật khẩu để dùng dần.
                - Gửi qua các phương tiện khác như SMS.
                - Sử dụng các thiết bị chuyên dụng (token,...).
            - Ưu điểm: An toàn hơn, tránh được tấn công kiểu replay (lấy được mật khẩu dùng lại).
            - Nhược điểm: Khó nhớ.

#### b) Điều khiển truy nhập dựa trên các khoá mã (Encrypted Keys):
- Là các giải thuật cho phép:
    - Đảm bảo an toàn thông tin bí mật.
    - Cho phép kiểm tra thông tin nhận dạng của các bên tham gia giao dịch.
- Ứng dụng rộng rãi nhất là chứng chỉ số (Digital Certificate). Một chứng chỉ số thường gồm các thuộc tính:
    - Thông tin nhận dạng chủ thể.
    - Khoá công khai của chủ thể.
    - Các thông tin nhận dạng và khoá công khai của chủ thể được mã hoá (ký) bởi một tổ chức có thẩm quyền (Certificate Authority - CA).
> - Biểu diễn chứng chỉ số của ngân hàng Vietcombank:
> 
> ![image](https://hackmd.io/_uploads/rkO2Zs6Y-l.png)
> ![image](https://hackmd.io/_uploads/SkUk7jaKWl.png)
> ![image](https://hackmd.io/_uploads/ryGlQiaKWl.png)

#### c) Điều khiển truy nhập dựa trên thẻ thông minh (Smart Card):
![image](https://hackmd.io/_uploads/r1nXNj6tWe.png)
- Là các thẻ nhựa có gắn các chip điện tử.
- Có khả năng tính toán và các thông tin lưu trong thẻ được mã hoá.
- Smart Card dùng hai yếu tố để xác thực và nhận dạng chủ thể:
    - Cái bạn có (What you have): Thẻ
    - Cái bạn biết (What you know): Mã PIN

#### d) Điều khiển truy nhập dựa trên token:
- Các token thường là các thiết bị cầm tay được thiết kế nhỏ gọn để có thể dễ dàng cầm theo (được tích hợp pin cung cấp nguồn nuôi).
- Token có thể được dùng để lưu:
    - Mật khẩu.
    - Thông tin cá nhân.
    - Các thông tin khác.
- Token thường được trang bị cơ chế xác thực hai yếu tố tương tự Smart Card:
    - CPU có năng lực xử lý cao hơn Smart Card.
    - Bộ nhớ lưu trữ lớn hơn.

![image](https://hackmd.io/_uploads/HJec4iTYbe.png)
![image](https://hackmd.io/_uploads/Hy6q4spYbl.png)
![image](https://hackmd.io/_uploads/Hkio4j6FWe.png)

#### e) Điều khiển truy nhập dựa trên các đặc điểm sinh trắc học (Biometric):
- Có thể dùng các đặc điểm sinh trắc học để nhận dạng chủ thể:
    - Dấu vân tay.
    - Tròng mắt.
    - Khuôn mặt.
    - Tiếng nói.
    - Chữ ký tay.
    - ...
- Ưu điểm:
    - Có khả năng bảo mật cao.
    - Luôn đi cùng chủ thể.
- Nhược điểm:
    - Chi phí đắt.
    - Chậm do đòi hỏi khối lượng tính toán lớn.
    - Tỷ lệ nhận dạng sai tương đối lớn do có nhiều yếu tố nhiễu ảnh hưởng.

## II. Tường lửa (Firewall):
### 1. Giới thiệu:
- Có thể là thiết bị phần cứng hoặc công cụ phần mềm được dùng để bảo vệ hệ thống và mạng cục bộ tránh các đe doạ từ bên ngoài.
- Tường lửa thường được đặt ở vị trí cổng vào của mạng nội bộ của công ty hoặc tổ chức.
- Tất cả gói tin từ trong ra và từ ngoài vào đều phải đi qua tường lửa.
- Chỉ các gói tin hợp lệ được phép đi qua tường lửa (xác định bởi chính sách an ninh, cụ thể hoá bằng luật).
- Bản thân tường lửa phải miễn dịch với các loại tấn công.
- Tường lửa có thể chặn nhiều hình thức tấn công mạng (như IP Spoofing).

### 2. Topo mạng với tường lửa:
![image](https://hackmd.io/_uploads/rklrTUZqZl.png)
![image](https://hackmd.io/_uploads/rJ_SaUW9-e.png)
![image](https://hackmd.io/_uploads/BJwLpLW9-l.png)

### 3. Các loại tường lửa:
#### a) Lọc gói tin (Packet-Filtering):
![image](https://hackmd.io/_uploads/r14MZjZqWl.png)
- Áp dụng một tập các luật cho mỗi gói tin đi/đến để quyết định chuyển tiếp hay loại bỏ gói tin.
- Các tường lửa dạng này thường lọc gói tin lớp IP.

##### Lọc có trạng thái (Stateful Firewall):
![image](https://hackmd.io/_uploads/H1Rd4o-5Zl.png)
- Có khả năng lưu trạng thái của các kết nối mạng đi qua nó.
- Được lập trình để phân biệt các gói tin thuộc về các kết nối mạng khác nhau.
- Chỉ những gói tin thuộc các kết nối mạng đang hoạt động mới được đi qua tường lửa, còn các gói tin khác (không thuộc kết nối đang hoạt động) sẽ bị chặn lại.

##### Lọc không trạng thái (Stateless Firewall):
- Lọc các gói tin riêng lẻ mà không quan tâm đến việc gói tin thuộc kết nối mạng nào.
- Dễ bị tấn công bởi kỹ thuật giả mạo địa chỉ, giả mạo nội dung gói tin do tường lửa không có khả năng nhớ các gói tin đi trước thuộc cùng một kết nối mạng.

##### Kỹ thuật kiểm soát truy nhập:
- Kiểm soát dịch vụ: Xác định dịch vụ nào có thể được truy nhập, hướng đi ra hay đi vào.
- Kiểm soát điều hướng: Điều khiển hướng được phép đi của các gói tin của mỗi dịch vụ.
- Kiểm soát người dùng:
    - Xác định user nào được quyền truy nhập.
    - Thường áp dụng cho người dùng mạng nội bộ.
- Kiểm soát hành vi: Kiểm soát việc dùng các dịch vụ cụ thể.
> Ví dụ: Tường lửa có thể lọc để loại bỏ các thư rác hoặc hạn chế truy nhập đến một bộ phận thông tin của máy chủ web.

##### Các hạn chế:
- Không thể chống lại các tấn công không đi qua nó.
- Không thể chống lại các tấn công hướng dữ liệu hoặc tấn công vào các lỗ hổng an ninh của các phần mềm.
- Không thể chống lại các hiểm hoạ từ bên trong (mạng nội bộ).
- Không thể ngăn chặn việc vận chuyển các chương trình hoặc các file bị nhiễm virus hoặc các phần mềm độc hại.

#### b) Các cổng ứng dụng (Application-level Gateway):
![image](https://hackmd.io/_uploads/HJXmZs-qZg.png)
- Còn gọi là proxy server, thường dùng để phát lại (relay) traffic của mức ứng dụng.
- Tường lửa ứng dụng web (WAF - Web Application Firewall) là dạng cổng ứng dụng được dùng rộng rãi.

#### c) Cổng chuyển mạch (Circuit-level Gateway):
![image](https://hackmd.io/_uploads/HkyVWiWcZl.png)
Hoạt động tương tự các bộ chuyển mạnh.

## III. Các hệ thống ngăn chặn/phát hiện tấn công, xâm nhập (IDS/IPS):
![image](https://hackmd.io/_uploads/H1CUIjZ5be.png)
- Các hệ thống phát hiện/ngăn chặn tấn công, xâm nhập (IDP/IPS) thường được dùng như một lớp phòng vệ quan trọng trong các lớp giải pháp đảm bảo an toàn cho hệ thống thông tin và mạng:
    - IDS - Intrusion Detection System: Hệ thống phát hiện tấn công, xâm nhập.
    - IPS - Intrusion Prevention System: Hệ thống ngăn chặn tấn công, xâm nhập.
- Các hệ thống IDS/IPS có thể được đặt trước hoặc sau tường lửa, tuỳ theo mục đích sử dụng.

#### a) Nhiệm vụ chính của các hệ thống IDS/IPS:
- Giám sát lưu lượng mạng hoặc các hành vi trên một hệ thống để nhận dạng các dấu hiệu của tấn công xâm nhập.
- Khi phát hiện các hành vi tấn công, xâm nhập thì ghi logs các hành vi này cho phân tích bổ sung sau này.
- Ngăn chặn hoặc dừng các hành vi tấn công, xâm nhập.
- Gửi thông báo cho admin về các hành vi tấn công, xâm nhập đã phát hiện được.

#### b) So sánh IDS/IPS:
- Giống: Về cơ bản giống nhau về chức năng giám sát.
- Khác:
    - IPS thường được đặt giữa đường truyền thông và có thể chủ động ngăn chặn các tấn công/xâm nhập bị phát hiện.
  
    ![image](https://hackmd.io/_uploads/r1fwvs-c-e.png)
    - IDS thường được kết nối vào các bộ định tuyến, switch, card mạng và chủ yếu làm nhiệm vụ giám sát/cảnh báo, không có khả năng chủ động ngăn chặn tấn công, xâm nhập.
  
    ![image](https://hackmd.io/_uploads/HJzUvj-cbx.png)

#### c) Phân loại:
##### Theo nguồn dữ liệu:
![image](https://hackmd.io/_uploads/SykruiZcbl.png)
- **Hệ thống phát hiện xâm nhập mạng (NIDS - Network-based IDS):** Phân tích lưu lượng mạng để phát hiện tấn công, xâm nhập cho cả mạng hoặc một phần mạng.
- **Hệ thống phát hiện xâm nhập cho host (HIDS - Host-based IDS):** Phân tích các sự kiện xảy ra trong hệ thống/dịch vụ để phát hiện tấn công, xâm nhập cho hệ thống đó.
    
##### Theo kỹ thuật phân tích:
- **Phát hiện xâm nhập dựa trên chữ kỹ hoặc phát hiện sự lạm dụng (Signature-based/Misue Intrucsion Detection):**
![image](https://hackmd.io/_uploads/rkMh_iWq-x.png)
    - Xây dựng database các chữ ký/dấu hiệu của các loại tấn công, xâm nhập đã biết.
        - Hầu hết các chữ ký/dấu hiệu được nhận dạng và mã hoá thủ công.
        - Dạng biểu diễn thường gặp là các rules phát hiện.
    - Giám sát các hành vi của hệ thống và cảnh báo nếu phát hiện chữ ký của tấn công, xâm nhập.
    - Ưu điểm:
        - Có khả năng phát hiện các tấn công, xâm nhập đã biết một cách hiệu quả.
        - Tốc độ cao, yêu cầu tài nguyên tính toán tương đối thấp.
    - Nhược điểm:
        - Không có khả năng phát hiện các tấn công, xâm nhập mới do chữ ký của chúng chưa có trong database các chữ ký.
        - Đòi hỏi nhiều công sức xây dựng và cập nhật database chữ ký/dấu hiệu tấn công, xâm nhập.
- **Phát hiện xâm nhập dựa trên các bất thường (Anomaly Instruction Detection):**
    - Phương pháp này dựa trên giả thiết: *Các hành vi xâm nhập thường có quan hệ chặt chẽ với các hành vi bất thường*
    - Quá trình xây dựng và triển khai gồm hai giai đoạn:
        - Xây dựng profile của đối tượng trong chế độ làm việc bình thường. Cần giám sát đối tượng trong điều kiện bình thường trong khoảng thời gian đủ dài để thu thập dữ liệu huấn luyện.
        - Giám sát hành vi hiện tại của hệ thống và cảnh báo nếu có khác biệt rõ nét giữa hành vi hiện tại và hồ sơ của đối tượng.
    > ![image](https://hackmd.io/_uploads/S1pNcjWqWx.png)
    > ![image](https://hackmd.io/_uploads/HyZ59iWcZg.png)
    - Ưu điểm: Có tiềm năng phát hiện các loại xâm nhập mới mà không yêu cầu biết trước thông tin về chúng.
    - Nhược điểm:
        - Tỷ lệ cảnh báo sai tương đối cao so với phương pháp dựa trên chữ ký.
        - Tiêu tốn tài nguyên hệ thống cho việc xây dựng hồ sơ đối tượng và phân tích hành vi hiện tại.
    - Các phương pháp xử lý, phân tích dữ liệu và mô hình hoá trong phát hiện xâm nhập dựa trên bất thường:
        - Thống kê (Statistics).
        - Machine Learning: HMM, Máy trạng thái (State-based).
        - Khai phá dữ liệu (Data mining).
        - Mạng nơ-ron (Neural Networks).
