## I. Khái quát về mã hoá thông tin và ứng dụng:
### 1. Mã hoá thông tin là gì?
- Định nghĩa theo Webster's Revised Unabridged Dictionary: `crytography is "the act or art of writing secret characters"` - Mật mã là một hành động hoặc nghệ thuật viết các ký tự bí mật.
- Định nghĩa theo Free Online Dictionary of Computing: `cryptography is "encoding data so that it can only be decoded by specific individuals"` - Mật mã là việc mã hoá dữ liệu mà nó chỉ có thể được giải mã bởi một số người chỉ định.
- Một hệ mã hoá gồm hai khâu:
    - Mã hoá (Encryption).
    - Giải mã (Decryption).
> ![image](https://hackmd.io/_uploads/ByZx8pBtWx.png)
- Các thuật ngữ:
    - Thông tin chưa được mã hoá (Unencrypted Information): Thông tin ở dạng có thể hiểu được, cũng được gọi là bản rõ (plaintext hay cleartext).
    - Thông tin đã được mã hoá (Encrypted Information): Thông tin ở dạng đã bị xáo trộn, cũng được gọi là bản mã (ciphertext hay encrypted text).
    - Mã hoá (Encryption): Hành động xáo trộn (scrambling) bản rõ để chuyển thành bản mã.
    - Giải mã (Decryption): Hành động giải xáo trộn (unscrambling) bản mã để chuyển thành bản rõ.
    - Mã hoá/Giải mã sử dụng thuật toán (Algorithm) để mã hoá/giải mã thông tin. Thuật toán mã hoá/giải mã có thể giống hoặc khác nhau.
    - Bộ mã hoá (Cipher): Giải thuật để mã hoá và giải mã thông tin.
    - Khoá/Chìa (Key): Chuỗi được dùng trong giải thuật mã hoá và giải mã.
    - Không gian khoá (Keyspace): Tổng số khoá có thể có của một hệ mã hoá.
    > Ví dụ: Nếu dùng khoá kích thước 64 bit thì không gian khoá là $2^64$.
    - Mã khoá bí mật (Secret Key Cryptography): Một khoá được dùng cho cả giải thuật mã hoá và giải mã, được gọi là khoá bí mật (secret key) hay khoá chia sẻ (shared key).
    - Mã khoá công khai (Public Key Cryptography): Một cặp khoá được dùng, trong đó:
        - Khoá để mã hoá là khoá công khai (Public key).
        - Khoá để giải mã là khoá riêng (Private key).
    - Hàm băm (Hash function): Ánh xạ chuyển các dữ liệu có kích thước thay đổi về dữ liệu có kích thước cố định. Hàm băm một chiều (One-way hash function) là hàm băm trong đó việc thực hiện mã hoá tương đối đơn giản, còn việc giải mã rất phức tạp hoặc không khả thi về mặt tính toán.
    > ![image](https://hackmd.io/_uploads/Hy6QOaBY-e.png)
    - Phá mã/Thám mã (Cryptanalysis): Quá trình giải mã bản mã mà không cần có trước:
        - Thông tin về giải thuật mã hoá (Encryption algorithm).
        - Thông tin về khoá (key).
          
        ![image](https://hackmd.io/_uploads/rkuFuTBFbg.png)

### 2. Vai trò của mã hoá:
Mã hoá có thể được dùng để đảm bảo an toàn thông tin trên đường truyền với các thuộc tính:
- Bí mật (Confidentiality): Đảm bảo chỉ những ai có thẩm quyền mới có khả năng truy nhập vào thông tin.
- Toàn vẹn (Integrity): Đảm bảo dữ liệu không bị sửa đổi bởi các bên không đủ quyền.
- Xác thực (Authentication): Thông tin nhận dạng về các chủ thể tham gia phiên truyền thông có thể xác thực.
- Không thể chối bỏ (Non-repudiation): Cho phép ngăn chặn chủ thể chối bỏ hành vi hoặc phát ngôn đã thực hiện.

### 3. Các thành phần của một hệ mã hoá:
- Một hệ mã hoá (Crypto system) được cấu từ hai thành phần chính:
    - Phương pháp mã hoá, hay giải thuật (Algorithm).
    - Tập các khoá, hay không gian khoá (Keyspace).
- Nguyên lý Kerckhoff: *"Tính an toàn của một hệ mã hoá không nên phụ thuộc vào việc giữ bí mật giải thuật mã hoá mà chỉ nên phụ thuộc vào việc giữ bí mật khoá mã"*

### 4. Lịch sử mã hoá:
- Các kỹ thuật mã hoá thô sơ đã được người Ai Cập cổ đại dùng cách đây 4000 năm.
- Người cổ Hy Lạp, Ấn Độ cũng dùng cách đây hàng nghìn năm.
- Các kỹ thuật mã hoá chỉ thực sự phát triển mạnh từ thế kỷ 1800 nhờ công cụ toán học và phát triển vượt bậc trong thế kỷ XX nhờ sự phát triển của máy tính và ngành Công nghệ Thông tin.
- Trong Chiến tranh Thế giới I và II, các kỹ thuật mã hoá được dùng rộng rãi trong liên lạc quân sự sử dụng sóng vô tuyến, dùng các công cụ phá mã/thám mã để giải mã thông điệp của quân địch.
- Năm 1976 chuẩn hoá DES (Data Encryption Standard) được Cơ quan An ninh Quốc gia Mỹ (NSA - National Security Agency) thừa nhận và sử dụng rộng rãi.
- Năm 1976, hai nhà khoa học Whitman Diffie và Martin Hellman đưa ra khái niệm mã hoá bất đối xứng (Asymetric Key Cryptography) hay mã hoá công khai (Public Key Cryptography), đưa đến những thay đổi lớn trong ngành mật mã:
    - Các hệ mã hoá khoá công khai hỗ trợ trao đổi khoá dễ dàng hơn.
    - Các hệ mã hoá bí mật gặp khó khăn trong quản lý trao đổi khoá, đặc biệt khi số lượng user lớn.
- Năm 1977, ba nhà khoa học Ronald Rivest, Adi Shamir và Leonard Adleman giới thiệu giải thuật mã hoá công khai RSA:
    - RSA trở thành giải thuật mã hoá công khai được dùng rộng rãi nhất.
    - RSA có thể dùng để mã hoá thông tin và trong chữ kí số.
- Năm 1991, phiên bản đầu tiên của chuẩn bảo mật PGP (Pretty Good Privacy) ra đời.
- Năm 2001, chuẩn mã hoá AES (Advanced Encryption Standard) được xây dựng và sử dụng rộng rãi.

### 5. Mã hoá dòng và mã hoá khối:
- Mã hóa dòng (Stream Cipher): Kiểu mã hóa mà từng bit (hoặc ký tự) của dữ liệu được kết hợp với từng bit (hoặc ký tự) tương ứng của khóa để tạo thành bản mã.

![image](https://hackmd.io/_uploads/Hk7MNRHtZg.png)
- Mã hóa khối (Block Cipher): Kiểu mã hóa mà dữ liệu được chia ra thành từng khối có kích thước cố định để mã hóa.

![image](https://hackmd.io/_uploads/Hk0N4RBYWx.png)
- Các chế độ hoạt động (Modes of Operation) hay cách chia khối của mã hóa khối:
    - ECB (Electronic Codebook): Cùng khối bản rõ đầu vào, khối bản mã giống nhau. Các khối bản mã hoàn toàn độc lập ($c_j = E_k(x_j)$).
    - CBC (Cipher-Block Chaining): Cùng khối bản rõ đầu vào, khối bản mã giống nhau với cùng khóa và vector khởi tạo (IV). Khối mã $c_j$ phụ thuộc vào khối rõ $x_j$ và các khối rõ trước đó ($x_1 - x_{j - 1}) thông qua khối mã $c_{j - 1}$ ($c_j = E_k(x_j \oplus c_{j - 1})$, $c_0 = IV$).
    - CFB (Cipher Feedback): Cùng khối bản rõ đầu bào, khối bản mã khác nhau. Khối mã $c_j$ phụ thuộc vào khối rõ $x_j$ và các khối rõ trước đó ($x_1 - x_{j - 1}$) thông qua khối mã $c_{j - 1}$ ($c_j = E_k(c_{j - 1} \oplus x_j)$, $c_0 = IV$).
    - OFB (Output Feedback): Cùng khối bản rõ đầu vào, khối bản mã khác nhau, Hệ thống sinh luồng khối khoá và XOR với các khối mã để tạo bản mã. Luồng khoá độc lập với bản rõ.

### 6. Các tiêu chuẩn đánh giá hệ mã hoá:
- Độ an toàn (Level of Security): Thường được đánh giá thông qua số lượng tính toán để có thể phá được hệ mã hoá.
- Hiệu năng (Performance): Có thể được đo bằng tốc độ mã hoá (bits/s).
- Tính năng (Functionality): Hệ thống có thể được dùng cho nhiều mục đích bảo mật.
- Chế độ hoạt động (Modes of Operation): Cung cấp các tính năng khác nhau theo chế độ hoạt động.
- Độ dễ cài đặt (Ease of Implementation): Độ khó của việc cài đặt thuật toán trong thực tế trên phần cứng hoặc phần mềm.

### 7. Ứng dụng của mã hoá:
Các kỹ thuật mã hoá được ứng dụng rộng rãi trong các hệ thống/công cụ/dịch vụ bảo mật:
- Dịch vụ xác thực (Kerbeous, RADIUS,...).
- Điều khiển truy nhập.
- Các công cụ đánh giá và phân tích logs.
- Các sản phẩm quản lý An toàn Thông tin.
- Các công cụ cho đảm bảo an toàn cho truyền thông không dây.
- Các nền tảng bảo mật như PKI, PGP,...
- Các giao thức bảo mật như SSL/TLS, SSH, SET, IPSec,...
- Các hệ thống như VPN,...
- ...

## II. Các phương pháp mã hoá:
### 1. Phương pháp thay thế:
- Là phương pháp thay thế một giá trị này với một giá trị khác:
    - Thay một ký tự bằng một ký tự khác.
    - Thay một bit bằng một bit khác.
    - Ceasar Cipher: Dịch ba chữ sang bên phải.
    > ![image](https://hackmd.io/_uploads/SJir3PUFbg.png)
- Số bộ chữ mã có thể là một hoặc nhiều:
    - Một 1 gốc $\rightarrow$ Một chữ mã: Dễ đoán theo sự lặp lại.
    - Một 1 gốc $\rightarrow$ Một trong $n$ chữ mã: Khó đoán do phức tạp hơn.
> ![image](https://hackmd.io/_uploads/S1Wi3wLYbe.png)

### 2. Phương pháp hoán vị (đổi chỗ):
- Thực hiện sắp xếp lại các giá trị trong một khối để tạo bản mã.
- Có thể thực hiện với từng bit hoặc byte (kí tự).
> - Khoá đổi chỗ (khối tám phần tử) tính từ bên phải:
> 
> ![image](https://hackmd.io/_uploads/B1EN6DLtbg.png)
> - Thực hiện đổi chỗ trong khối tám ký tự, tính từ bên phải:
> 
> ![image](https://hackmd.io/_uploads/HJ9B6vUYZe.png)

### 3. Phương pháp XOR:
![image](https://hackmd.io/_uploads/Bkyqpw8t-e.png)
Phương pháp XOR dùng phép toán logic XOR để tạo bản mã. Từng bit của bản rõ được XOR với bit tương ứng của khoá.
> ![image](https://hackmd.io/_uploads/B1vo6PLtbg.png)

### 4. Phương pháp Vernam:
Dùng một tập ký tự để nối vào các ký tự của bản rõ để tạo bản mã. Mỗi ký tự trong tập chỉ dùng một lần trong một tiến trình mã hoá (gọi là one-time pad).
> Ví dụ: Với bộ chữ tiếng Anh có 26 chữ:
> 
> ![image](https://hackmd.io/_uploads/S1bSCvLFZe.png)
> - Các ký tự của bản rõ được chuyển thành số trong khoảng 1 - 26.
> - Cộng giá trị của ký tự với giá trị tương ứng trong tập nối thêm.
> - Nếu giá trị cộng lớn hơn 26 thì trừ cho 26 (phép module).

### 5. Phương pháp sách hoặc khoá chạy:
Thường được dùng trong các bộ phim trinh thám, trong đó việc mã hoá và giải mã dùng các khoá mã chứa trong các cuốn sách.
> ![image](https://hackmd.io/_uploads/SyC_Cw8tWl.png)

### 6. Phương pháp hàm băm:
- Là các thuật toán tạo các bản tóm tắt của thông điệp được dùng để nhận dạng và đảm bảo tính toàn vẹn của thông điệp.
    - Hàm băm: Hàm công khai được dùng để tạo giá trị băm hay thông điệp rút gọn (message digest).
    - Chiều dài của thông điệp là bất kì nhưng đầu ra có chiều dài cố định.
- Một số hàm băm thông dụng:
    - MD2, MD4, MD5 (128 bit).
    - MD6 (0 - 512 bit).
    - SHA0, SHA1 (160 bit).
    - SHA2 (SHA256, SHA384, SHA512), SHA3.
    - CRC32 (32 bit).

## III. Các giải thuật mã hoá:
### 1. Giải thuật mã hoá khoá đối xứng (Sysmetric Key Encryption):
![image](https://hackmd.io/_uploads/S1CXW_Ut-e.png)
- Còn gọi là mã khoá khoá riêng bí mật (Secret/Private Encryption).
- Dùng một khoá (key) duy nhất cho cả quá trình mã hoá và giải mã.
- Đặc điểm:
    - Kích thước khoá tương đối ngắn (64, 128, 192, 256 bits).
    - Tốc độ nhanh.
    - Độ an toàn cao.
    - Khó khăn trong quản lý và phân phối khoá.

#### a) DES, Triple-DES:
##### DES (Data Encryption Standard):
- Được phát triển tại IBM đầu những năm 1970s.
- Được thừa nhận là chuẩn mã hoá tại Mỹ (NSA) năm 1976.
- Được dùng rộng rãi trong những năm 70s và 80s.
- Hiện nay không được coi là an toàn do:
    - Không gian khoá nhỏ (khoá 64 bit, trong đó thực sử dụng 56 bit).
    - Tốc độ tính toán của các hệ thống máy tính ngày càng nhanh.
- Đặc điểm:
    - Là dạng mã hoá khối, kích thước khối vào 64 bit.
    - Khoá 64 bit, thực sử dụng 56 bit, 8 bit dùng cho kiểm tra chẵn lẻ.
    - DES dùng chung một giải thuật cho cả mã hoá và giải mã.
- Mã hoá và giải mã một khối dữ liệu:

![image](https://hackmd.io/_uploads/Sk7HGO8Ybl.png)
- Các bước thực hiện mã hoá của DES với mỗi khối dữ liệu 64 bit:
    - Bước hoán vị khởi tạo (IP - Initial Permulatation): Chia khối 64 bit thành hai khối 32 bit và xử lý lần lượt.
    - Lặp 16 vòng chính thực hiện xáo trộn dữ liệu theo hàm Feistel (F). Các bước thực hiện:
  
    ![image](https://hackmd.io/_uploads/SyYHQdUFWx.png)
        - E (Expansion): Mở rộng 32 bit đầu vào thành 48 bit bằng cách nhân đôi một nửa số bit.
        - $\oplus$: Trộn 48 bit trên với khoá phụ 48 bit. Có 16 khoá phụ được tạo từ khoá chính để dùng cho 16 vòng lặp. Cách tạo bộ khoá phụ cho 16 vòng lặp:
        ![image](https://hackmd.io/_uploads/H1C-Su8F-e.png)
            - 56 bit khoá được chọn từ khoá 64 bit ban đầu bởi PC1 (Permuted Choice 1), 8 bit còn lại được huỷ hoặc dùng để kiểm tra chẵn lẻ.
            - 56 bit được chia thành hai phần 28 bit, mỗi phần được xử lý riêng.
            - Mỗi phần được quay trái 1 hoặc 2 bit.
            - Hai phần được ghép lại và 48 bit được chọn làm khoá phụ 1 bởi PC2.
            - Lặp lại các bước trên để tạo 15 khoá phụ còn lại.
        - $S_i$ (Substitution): Khối dữ liệu 48 bit được chia thành tám khối 6 bit và được chuyển cho các bộ thay thế ($S_1$ - $S_8$). Mỗi bộ thay thế dùng phép chuyển đổi phi tuyến tính để chuyển 6 bit đầu vào thành 4 bit đầu ra theo bảng tham chiếu. Các bộ thay thế là thành phần nhân an ninh (Security Core) của DES.
        - $P$: 32 bit đầu ra từ các bộ thay thế được sắp xếp bằng phép hoán vị cố định (Fixed Permutation) cho ra đầu ra 32 bit.
    - Bước hoán vị kết thúc (FP - Final Permulatation).
- Tiến trình mã hoá một khối dữ liệu với DES:

![image](https://hackmd.io/_uploads/Syp0z_LY-e.png)
- Dùng phép $\oplus$ (XOR) để kết hợp trong quá trình lặp.
- Giải mã trong DES:
    - Có thể dùng giải thuật mã hoá DES để giải mã.
    - Các bước thực hiện giống quá trình mã hoá.
    - Các khoá phụ dùng cho các vòng lặp được dùng theo trật tự ngược lại: Khoá phụ 16, 15,..., 2, 1 cho các vòng 1, 2,..., 15, 16 tương ứng.

##### Triple-DES (3-DES):
![image](https://hackmd.io/_uploads/r1vu8dIFZl.png)
- Còn được gọi là Triple Data Encryption Algorithm (TDEA hoặc Triple DEA) được phát triển từ DES bằng cách áp dụng DES ba lần cho mỗi khối dữ liệu.
- Dùng bộ ba khoá DES $K_1$, $K_2$, $K_3$ , mỗi khoá kích thước hiệu dụng 56 bit.
- Các lựa chọn bộ khoá:
    - Lựa chọn 1: Cả ba khoá độc lập (168 bit).
    - Lựa chọn 2: $K_1$ và $K_2$ độc lập, $K_3 = K_1$ (112 bit).
    - Lựa chọn 3: Ba khoá giống nhau, $K_1 = K_2 = K_3$ (56 bit).
- Kích thước khối dữ liệu đầu vào là 64 bit.
- Giải thuật mã hoá: $$C = E_{K_3}(D_{K_2}(E_{K_1}(P)))$$ $\rightarrow$ Mã hoá bằng $K_1$, giải mã bằng $K_2$ và mã hoá bằng $K_3$.
- Giải thuật giải mã: $$P = D_{K_1}(E_{K_2}(D_{K_3}(C)))$$ $\rightarrow$ Giải bằng $K_3$, mã hoá bằng $K_2$ và giải mã bằng $K_1$.

##### AES (Advanced Encryption Standard):
- Là chuẩn mã hoá dữ liệu được NIST công nhận năm 2001.
- Được xây dựng dựa trên Rijndael Cipher phát triển bởi hai nhà mật mã học người Bỉ là Joan Daeman và Vincent Rijmen.
    - Rijndael Cipher là bộ mã hoá được chọn để xây dựng AES sau khi giành chiến thắng trong cuộc thi tuyển chọn bộ mã hoá làm chuẩn mã hoá mới thay cho DES.
    - AES về cơ bản giống như Rijndael Cipher.
- Đặc điểm:
    - Kích thước khối dữ liệu là 128 bit.
    - Kích thước khoá có thể là 128, 192 hoặc 256 bit.
    - Được thiết kế dựa trên mạng hoán vị - thay thế (Subsititution - Permutation Network), có thể đạt tốc độ cao trên cả cài đặt phần cứng và phần mềm.
- Vận hành dựa trên ma trận 4x4 được gọi là `state` (Trạng thái).
- Kích thước của khoá quyết định số vòng lặp chuyển đổi cần thực hiện để chuyển bản rõ thành bản mã:
    - Mười vòng lặp với khoá 128 bit.
    - 12 vòng lặp với khoá 192 bit.
    - 14 vòng lặp với khoá 256 bit.
- Mô tả khái quát giải thuật AES:

![image](https://hackmd.io/_uploads/Hycn5OUYZg.png)
    - Mở rộng khoá (KeyExpansion): Các khoá phụ dùng trong các vòng lặp được sinh ra từ khoá chính AES sử dụng thủ tục sinh khoá Rijndael:
    ![image](https://hackmd.io/_uploads/Sy8Fsu8KZx.png)
        - Rotword: Quay trái 8 bit.
        - SubBytes
        - Rcon: Tính toán giá trị: $rcon(i) = x^{i - 1} \mod x^8 + x^4 + x^3 + x + 1$
        - ShiftRow
    - Vòng khởi tạo (IntialRound): AddRoundKey - Mỗi byte trong `state` được kết hợp với khoá phụ sử dụng XOR.
    - Các vòng lặp chính (Rounds):
        - SubBytes: Bước thay thế phi tuyến tính, trong đó mỗi byte trong `state` được thay thế bằng một byte khác sử dụng bảng tham chiếu Rijndael S-box, hay $b_{ij} = S(a_ij)$.
        ![image](https://hackmd.io/_uploads/SyNTou8tbl.png)
        - ShiftRows: Bước đổi chỗ, trong đó mỗi dòng trong `state` được dịch sang trái một số bước theo chu kỳ, dòng thứ nhất giữ nguyên.
        ![image](https://hackmd.io/_uploads/B1Ak3_UtWe.png)
        - MixColumns: Mỗi cột trong `state` được nhân với một đa thức $c(x)$, kết hợp 4 byte trong mỗi cột.
        ![image](https://hackmd.io/_uploads/HyOfh_IKbx.png)
        - AddRoundKey: XOR mỗi byte của ma trận `state` với mỗi byte khóa phụ tương ứng, là bước đưa yếu tố khóa bí mật vào quá trình biến đổi.
    - Vòng cuối (Final Round, không MixColumns):
        - SubBytes
        - ShiftRows
        - AddRoundKey
- Quá trình mã hoá và giải mã:

![image](https://hackmd.io/_uploads/HkcK3_UYbl.png)

#### b) Blowfish, Twofish:
#### c) RC4, RC5:

### 2. Giải thuật mã hoá khoá bất đối xứng (Asymetric Key Encryption):
![image](https://hackmd.io/_uploads/Bk_NTOUYbx.png)
- Còn gọi là mã hoá khoá công khai (Public Key Encryption).
- Dùng một cặp khoá (Key Pair):
    - Khoá công khai (Public Key) cho mã hoá.
    - Khoá riêng (Private Key) cho giải mã.
- Đặc điểm:
    - Kích thước khoá lớn (1024 - 3072 bit).
    - Tốc độ chậm, phần lớn do khoá có kích thước lớn.
    - Độ an toàn cao.
    - Thuận lợi trong quản lý và phân phối khoá do khoá mã hoá là công khai và có thể trao đổi dễ dàng.
- Các giải thuật mã hoá bất đối xứng điển hình:

#### a) RSA:
- Được ba nhà khoa học Ronald Rives, Adi Shamir và Leonard Adleman phát minh năm 1977. Tên giải thuật lấy theo chữ cái đầu tên ba ông.
- Độ an toàn dựa trên tính phức tạp của việc phân tích số nguyên lớn vì khoá RSA là số nguyên rất lớn có hàng trăm chữ số thập phân.
- RSA dùng một cặp khoá:
    - Khoá công khai (Public Key) để mã hoá.
    - Khoá riêng (Private Key) để giải mã.
    - Chỉ khoá riêng cần giữ bí mật, khoá công khai có thể công bố rộng rãi.
- Kích thước khoá:
    - Khoá nhỏ hơn 1024 bit không an toàn.
    - Khuyến nghị dùng khoá lớn hon 2048 bit với các ứng dụng mật mã dân sự hiện nay.
    - Tương lai nên dùng khoá lớn hơn 3072 bit.
- Thủ tục sinh khoá RSA:
    - Tạo hai số nguyên tố $p$ và $q$.
    - Tính $n = p.q$.
    - Tính $\phi(n) = (p - 1)(q - 1).
    - Chọn số nguyên tố $e$ sao cho $0 < e < \phi(n)$ và $GCD(e, \phi(n)) = 1$, hay $e$ và $\phi(n)$ là hai số nguyên tố cùng nhau.
    - Chọn $d$ sao cho $d \equiv e^{-1} \mod \phi(n)$ hay $d.e \equiv 1 \mod \phi(n)$ ($d$ là modulo nghịch đảo của $e$.
    - Ta có $(n, e)$ là khoá công khai và $(n, d)$ là khoá riêng.
- Thủ tục mã hoá:
    - Thông điệp $m$ được chuyển thành số, $m < n$.
    - Bản mã $c = m^e \mod n$.
- Thủ tục giải mã:
    - Bản mã $c < n$.
    - Bản rõ $m = c^d \mod n$.
> Ví dụ:
> - Chọn hai số nguyên tố $p = 3$ và $q = 11$.
> - Tính $n = p.q = 3.11 = 33$.
> - Tính $\phi(n) = (p - 1)(q - 1) = 2.10 = 20$.
> - Chọn $e$ sao cho $0 < e < 20$, $e$ và $\phi(n)$ là số nguyên tố cùng nhau. Chọn $e = 7$.
> - Chọn $d$ sao cho $d.e \equiv 1 \mod \phi(n)$. Chọn $d = 3$.
> - Khoá công khai là $(33, 7)$ và khoá bí mật là $(33, 3)$.
> - Mã hoá: Với $m = 6$, $c = m^e \mod n = 6^7 \mod 33 = 279936 \mod 33 = 30$
> - Giải mã: $m = c^d \mod n = 30^3 \mod 33 = 27000 \mod 33 = 6$
- Một số yêu cầu với quá trình sinh khoá:
    - Các số nguyên tố $p$ và $q$ phải được chọn sao cho việc phân tích $n$ không khả thi về mặt tính toán.
    - $p$ và $q$ nên cùng độ lớn (tính bằng bit) và phải là các số đủ lớn:
        - Nếu $n$ có kích thước 1024 bit thì $p$ và $q$ nên có kích thước khoảng 512 bit.
        - Nếu $n$ có kích thước 2048 bit thì $p$ và $q$ nên có kích thước khoảng 1024 bit.
    - Hiệu số $p - q$ không nên quá nhỏ, tức $p \approx q$ và $p \approx \sqrt{n}$, có thể chọn các số nguyên gần $\sqrt{n}$ để thử nhiều lần.
    - Khi có được $p$ thì tính $q$ và tìm ra $d$ là khoá bí mật từ khoá công khai $e$ và $\phi(n)$.
    - Nếu $p$ và $q$ được chọn ngẫu nhiên và $p - q$ đủ lớn, khả năng hai số này bị phân tích từ $n$ bị giảm đi.
- Sử dụng số mũ mã hoá $e$ nhỏ:
    - Khi dùng số mũ $e$ nhỏ, chẳng hạn $e = 3$, có thể tăng tốc độ mã hoá.
    - Khi kẻ tấn công có thể nghe trộm và lấy được bản mã, từ đó phân tích bản mã để khôi phục bản rõ. Do số mũ nhỏ nên chi phí cho việc phân tích/brute-force không quá lớn.
    - Phòng chống:
        - Dùng $e$ lớn.
        - Thêm chuỗi ngẫu nhiên vào khối rõ trước khi mã hoá.
- Sử dụng số mũ giải mã $d$ nhỏ:
    - Có thể tăng tốc độ giải mã.
    - Nếu $d$ nhỏ và $GCD(p - 1, q - 1)$ cũng nhỏ thì $d$ có thể dễ dàng tính được từ khoá công khai $(n, e)$.
    - Phòng chống: Dùng số mũ $d$ đủ lớn.
- Cài đặt RSA trên thực tế:
    - Do kích thước của cặp khoá RSA rất lớn ($n$ cỡ 2048 bit, khoảng hơn 600 chữ số thập phân), việc thực hiện RSA trực tiếp có chi phí rất lớn (Do $m$, $e$, $d$ thường rất lớn nên giá trị $m^e$ và $c^d$ thường rất rất lớn).
    - Cần có giải thuật hiệu quả để giảm chi phí tính toán nên cần cài đặt trên máy tính.
- Cài đặt trong Java:
    - Java định nghĩa lớp Biglnteger cung cấp hầu hết các hàm dựng và các hàm số học cho phép thao tác thuận lợi với số nguyên lớn.
    - Một số hàm có thể dùng để cài đặt RSA:
  
    ![image](https://hackmd.io/_uploads/SywT9WuYbx.png)
- Cài đặt trên ngôn ngữ C:
    - Do thư viện C không hỗ trợ số lớn nên việc cài đặt RSA trong C phải thực hiện từ các thao tác số học cơ sở.
    - Có thể dùng một mảng để lưu các chữ số của số nguyên lớn và xây dựng các hàm thực hiện các phép toán số học và modulo cho số nguyên lớn.
    - Lựa chọn cơ số:
        - Cơ số $10$: Đơn giản, dễ hiểu nhưng tốn không gian lưu trữ và chậm do không tận dụng được khả năng thực hiện các phép toán nhân chia với số $2$ thông qua phép dịch. Cơ số nên là số mũ của $2$ và cần đủ lớn.
        - Cơ số $256$: Một số được lưu trong một phần tử mảng là một byte nên tiết kiệm không gian lưu trữ. Tuy nhiên số phần tử mảng vẫn có thể khá lớn nên chậm trong thao tác.
        - Cơ số $2^{16} (65536)$: Khá phù hợp do một số được lưu trong một phần tử mảng là hai byte và số phần tử mảng sẽ giảm nên nhanh hơn trong thao tác.
    - Định nghĩa cấu trúc BigInt:
  
    ![image](https://hackmd.io/_uploads/ByyG3WdYbe.png)

#### b) Rabin:
#### c) ElGamal:
#### d) McEliece:
#### e) Knapsack:

### 3. Các hàm băm (Hash Function):
- Là một hàm toán học $h$ có tối thiểu hai thuộc tính cơ bản:
    - Nén (Compression): $h$ là một ánh xạ từ chuỗi đầu vào $x$ có chiều dài bất kì sang một chuỗi đầu ra $h(x)$ có chiều dài cố định $n$ bit.
    - Dễ tính toán (Ease of Computation): Cho trước hàm $h$ và đầu vào $x$, việc tính toán $h(x)$ là dễ dàng.
- Phân loại hàm băm theo khoá sử dụng:

![image](https://hackmd.io/_uploads/r1uzRb_Y-g.png)
    - Hàm băm không khoá (Unkeyed): Đầu vào chỉ là thông điệp.
    - Hàm băm có khoá (Keyed): Đầu vào gồm thông điệp và khoá.
- Phân loại hàm băm theo tính năng:
    - Mã phát hiện sửa đổi (MDC - Modification Detection Codes).
        - Thường được dùng để tạo chuỗi đại diện cho thông điệp và dùng kết hợp với các biện pháp khác để đảm bảo tính toàn vẹn của thông điệp.
        - Thuộc hàm băm không khoá.
        - Thường được dùng trong các quá trình tạo và kiểm tra chữ ký số để đảm bảo tính toàn vẹn thông điệp.
        - Hai loại MDC:
            - Hàm băm một chiều (OWHF - One-way Hash Functions): Dễ dàng tính giá trị băm nhưng khôi phục thông điệp từ giá trị băm rất khó khăn.
            - Hàm băm chống đụng độ (CRHF - Collision Resistant Hash Functions): Rất khó tìm được hai thông điệp trùng giá trị băm.
    - Mã xác thực thông điệp (MAC - Message Authentication Codes):
        - Cũng được dùng để đảm bảo tính toàn vẹn của thông điệp mà không cần một biện pháp bổ sung khác.
        - Là loại hàm băm có khoá, đầu vào là thông điệp và một khoá.
        - Được dùng trong các giao thức bảo mật SSL/TLS, IPSec,... để đảm bảo tính toàn vẹn thông điệp.
- Mô hình lặp tổng quát tạo giá trị băm:

![image](https://hackmd.io/_uploads/rJdh1zuKWg.png)
- Mô hình lặp chi tiết tạo giá trị băm:

![image](https://hackmd.io/_uploads/Bkq5yGOtbx.png)
- Một số giải thuật hàm băm điển hình:

#### a) MD2, MD4, MD5, MD6:
##### MD5 (Message Digest):
- Là hàm băm không khoá được Ronald Rivest thiết kế năm 1991 để thay thế MD4.
- Chuỗi đầu ra (giá trị băm) của MD5 là 128 bit (16 byte) và thường được biểu diễn thành 32 số hexa.
- Được dùng khá rộng rãi trong nhiều ứng dụng:
    - Chuỗi đảm bảo tính toàn vẹn thông điệp.
    - Tạo chuỗi kiểm tra lỗi - Checksum.
    - Mã hoá mật khẩu.
- Quá trình xử lý thông điệp của MD5:
    - Thông điệp được chia thành các khối 512 bit. Nếu kích thước thông điệp không phải bội số của 512 thì nối thêm số bit thiếu.
    - Phần xử lý chính của MD5 làm việc trên state 128 bit, chia thành bốn từ 32 bit ($A$, $B$, $C$, $D$):
        - Các từ $A$, $B$, $C$, $D$ được khởi trị bằng một hằng cố định.
        - Từng phần 32 bit của khối đầu vào 512 bit được đưa dần vào để thay đổi state.
    - Quá trình xử lý gồm bốn vòng, mỗi vòng gồm 16 thao tác tương tự nhau. Mỗi thao tác gồm:
        - Hàm $F$ (bốn hàm khác nhau cho mỗi vòng).
        - Cộng modulo.
        - Quay trái.
- Lưu đồ xử lý một thao tác của MD5:

![image](https://hackmd.io/_uploads/S1eINfdYZe.png)
    - $A$, $B$, $C$, $D$: Các từ 32 bit.
    - $M_i$: Khối 32 bit thông điệp đầu vào.
    - $K_i$: Là 31 bit hằng, mỗi thao tác dùng một hằng khác nhau.
    - $<<<s$: Thao tác dịch trái $s$ bit.
    - $\boxplus$: Biểu diễn cộng modulo 32 bit.
    - $F$: Hàm phi tuyến tính, gồm bốn loại:
        - $F(B,C,D) = (B \land V) \lor (\neg{B} \land D)$
        - $G(B,C,D) = (B \land D) \lor (C \land \neg{D})$
        - $H(B,C,D) = B \oplus C \oplus D$
        - $I(B,C,D) = C \oplus (B \lor \neg{D})$

#### b) SHA0, SHA1, SHA2, SHA3:
Họ hàm băm SHA: SHA-0, SHA-1, SHA-2, SHA-3:
- SHA0 ít được sử dụng trên thực tế.
- SHA1 tương tự SHA0 nhưng đã khắc phục một số lỗi.
- SHA2 ra đời năm 2001, khắc phục lỗi của SHA1 và có nhiều thay đổi. Kích thước chuỗi đầu ra có thể là 224, 256, 384 và 512 bit.
- SHA3 ra đời năm 2012, cho phép chuỗi đầu ra có kích thước không cố định.

##### SHA1 (Secure Hash Function):
- Được NSA (Mỹ) thiết kế năm 1995 để thay thế SHA0.
- Chuỗi đầu ra của SHA1 có kích thước 160 bit và thường được biểu diễn thành 40 số hexa.
- Được dùng rộng rãi để:
    - Đảm bảo tính xác thực và toàn vẹn thông điệp.
    - Mã hoá mật khẩu.
- Quá trình xử lý thông điệp của SHA1:
    - Dùng thủ tục xử lý thông điệp tương tự MD5.
    - Thông điệp được chia thành các khối 512 bit. Nếu kích thước thông điệp không là bội số của 512 thì nối thêm số bit thiếu.
    - Phần xử lý chính của SHA1 làm việc trên state 160 bit, chia thành năm từ 32 bit ($A$, $B$, $C$, $D$, $E$):
        - Các từ $A$, $B$, $C$, $D$, $E$ được khởi trị bằng một hằng cố định.
        - Từng phần 32 bit của khối đầu vào 512 bit được đưa dần vào để thay đổi state.
    - Quá trình xử lý gồm 80 vòng, mỗi vòng gồm các thao tác: add, and, or, XOR, rotate, mod.
- Lưu đồ xử lý một vòng của SHA1:

![image](https://hackmd.io/_uploads/S161PzOtZl.png)
    - $A$, $B$, $C$, $D$, $E$: Các từ 32 bit.
    - $W_t$: Khối 32 bit thông điệp đầu vào.
    - $K_t$: Là 32 bit hằng, mỗi sử dụng một hằng khác nhau.
    - $<<<n$: Thao tác dịnh trái $n$ bit.
    - $\boxplus$: Biểu diễn cộng modulo 32 bit.
    - $F$: Hàm phi tuyến tính.

#### c) CRC (Cyclic Redundancy Checks):
#### d) Checksums:

## IV. Chữ ký số, chứng chỉ số và PKI:
### 1. Chữ ký số:
![image](https://hackmd.io/_uploads/rJBGnGYtWl.png)
![image](https://hackmd.io/_uploads/HJBrnMKFWg.png)

#### a) Khái niệm:
- Chữ ký số (Digital Signature) là một chuỗi dữ liệu liên kết với một thông điệp (message) và thực thể tạo ra thông điệp.
- Giải thuật tạo chữ ký số (Digital Signature Generation Algorithm) là một phương pháp sinh chữ ký số.
- Giải thuật kiểm tra chữ ký số (Digital Signature Verification Algorithm) là một phương pháp xác minh tính xác thực của chữ ký số, nghĩa là nó thực sự được tạo ra bởi một bên chỉ định.
- Một hệ chữ ký số (Digital Signature Scheme) gồm giải thuật tạo chữ ký số và giải thuật kiểm tra chữ ký số.
- Quá trình tạo chữ ký số (Digital Signature Signing Process) gồm:
    - Giải thuật tạo chữ ký số.
    - Phương pháp chuyển dữ liệu thông điệp thành dạng có thể ký được.
- Quá trình kiểm tra chữ ký số (Digital Signature Verification Process) gồm:
    - Giải thuật kiểm tra chữ ký số.
    - Phương pháp khôi phục dữ liệu từ thông điệp.

#### b) Quá trình ký và kiểm tra chữ ký số:
![image](https://hackmd.io/_uploads/SyEN0GYKWg.png)
- Các bước của quá trình ký một thông điệp (bên người gửi):
    - Tính toán chuỗi đại diện (Message Digest/Hash value) của thông điệp sử dụng một giải thuật băm (Hashing Algorithm).
    - Chuỗi đại diện được ký bằng cách dùng khoá riêng của người gửi và một giải thuật tạo chữ ký. Kết quả là chữ ký số của thông điệp hay còn gọi là chuỗi đại diện được mã hoá (Encrypted Message Digest).
    - Thông điệp ban đầu (Message) được ghép với chữ ký số tạo thành thông điệp đã được ký (Signed Message) rồi gửi cho người nhận.
- Các bước của quá trình kiểm tra chữ ký (bên người nhận):
    - Tách chữ ký số và thông điệp gốc khỏi thông điệp đã ký để xử lý riêng.
    - Tính toán chuỗi đại diện MD1 (Message Digest) của thông điệp gốc bằng cánh dùng giải thuật băm (giải thuật dùng trong quá trình ký).
    - Dùng khoá công khai của người gửi để giải mã chữ ký số $\rightarrow$ CHuỗi đại diện thông điệp MD2.
    - So sánh MD1 và MD2:
        - Nếu MD1 = MD2: Chữ ký kiểm tra thành công, thông điệp đảm bảo tính toàn vẹn và thực sự xuất phát từ người gửi (do khoá công khai được chứng thực).
        - Nếu MD1 $\neq$ MD2: Chữ ký không hợp lệ, thông điệpc có thể đã bị sửa đổi hoặc không thực sự xuất phát từ người gửi.

#### c) Thuật toán chữ ký số RSA:
![image](https://hackmd.io/_uploads/rkhwAfttZe.png)
RSA là giải thuật cho phép thực hiện hai tính năng:
- Mã hoá thông điệp:
    - Người gửi mã hoá thông điệp bằng cách dùng khoá công khai của người nhận.
    - Người nhận giải mã thông điệp bằng cách dùng khoá riêng của mình.

#### d) Thuật toán chữ ký số DSA:
- DSA (Digital Signature Algorithm) là chuẩn chữ ký số được phát triển bởi NIST (Mỹ) năm 1991.
- DSA được phát triển từ giải thuật Digital Signature Standard (DSS).
- Các thành phần của DSA:
    - Sinh khoá: Sinh cặp khoá, gồm hai giai đoạn:
        - Lựa chọn tham số của giải thuật.
            - Lựa chọn giải thuật băm chuẩn $H$. Giải thuật băm có thể được chọn là SHA1 hoặc SHA2.
            - Chọn kích thước cho các khoá $L$ và $N$:
                - $L$ có thể là 1024, 2048, 3072.
                - $N$ có thể là 160, 224, 256. N phải nhỏ hơn hoặc bằng kích thước chuỗi băm đầu ra của hàm H đã chọn.
                - Chọn số nguyên tố $q$ $N$ bit.
                - Chọn modulo $p$ $L$ bit sao cho $p - 1$ là bội số của $q$.
                - Chọn $g$ là hệ số nhân sao cho $g.q \equiv 1 \mod p$.
                - Các tham số $(q, p, g)$ được chia sẻ giữa các người dùng.
        - Sinh cặp khoá cho một người dùng:
            - Chọn số ngẫu nhiên $x$ sao cho $0 < x < q$.
            - Tính $y = g^x \mod p$.
            - Khoá công khai là $(q, p, g, y)$, khoá riêng là $x$.
    - Quá trình ký thông điệp:
        - $H$ là hàm băm sử dụng và $m$ là thông điệp gốc, tính $H(m)$.
        - Tạo số ngẫu nhiên $k$ cho mỗi thông điệp, $0 < k < q$.
        - Tính $r = (g^k \mod p) \mod q$. Nếu $r = 0$, chọn lại $k$ mới và tính lại $r$.
        - Tính $s = k^{-1}(H(m) + x.r) \mod q$. Nếu $s = 0$, chọn một $k$ mới và tính lại $r$ và $s$.
        - Chữ ký là cặp $(r, s)$.
    - Quá trình kiểm tra chữ ký của thông điệp:
        - Loại bỏ chữ ký nếu $r$ và $s$ không thoả $0 < r$, $s < q$.
        - Tính $H(m)$ từ thông điệp nhận được.
        - Tính $w = s^{-1} \mod q$.
        - Tính $u_1 = H(m).w \mod q$.
        - Tính $u_2 = r.w \mod q$.
        - Tính $v = ((g^{u_1}.y^{u_2}) \mod p) \mod q$.
        - Chữ ký là xác thực nếu $v = r$.
    
### 2. Chứng chỉ số (Digital Certificate):
#### a) Giới thiệu:
- Còn gọi là chứng chỉ công khai (Public Key Certificate) hay chứng chỉ nhận dạng (Identify Certificate), là một tài liệu điện tử sử dụng một **chữ ký số** để liên kết một **khoá công khai** và **thông tin nhận dạng** của một thực thể:
    - Chữ ký số: Chữ ký của một bên thứ ba tin cậy, thường gọi là CA - Certificate Authority.
    - Khoá công khai: Khoá công khai trong cặp khoá công khai của thực thể.
    - Thông tin nhận dạng: Tên, địa chỉ, tên miền hoặc các thong tin định danh của thực thể.
- Chứng chỉ số có thể được dùng để xác minh chủ thể thực sự của một khoá công khai.

#### b) Nội dung:
![image](https://hackmd.io/_uploads/HJz1SQKFbg.png)
![image](https://hackmd.io/_uploads/rJCkrQtF-x.png)
Chứng chỉ số gồm các trường chính:
- Serial Number: Số nhận dạng của chứng chỉ số.
- Subject: Thông tin nhận dạng một cá nhân hoặc tổ chức:
    - CN (Common Name): Tên chung, nhưng một tên miền được gán chứng chỉ.
    - OU (Organisation Unit): Tên bộ phận/phòng ban.
    - O (Organisation): Tổ chức/Cơ quan/Công ty.
    - L (Location): Địa điểm/Quận huyện.
    - S (State/Province): Bang/Tỉnh/Thành phố.
    - C (Country): Đất nước.
- Signature Algorithm: Giải thuật tạo chữ ký.
- Signature Hash Algorithm: Giải thuật tạo chuỗi băm cho việc tạo chữ ký.
- Signature: Chữ ký của người/tổ chức cấp chứng chỉ.
- Issuer: Người/Tổ chức có thẩm quyền/tin cậy cấp chứng chỉ.
- Valid-From: Ngày bắt đầu có hiệu lực của chứng chỉ.
- Valid-To: Ngày hết hạn sử dụng chứng chỉ.
- Key-Usage: Mục đích sử dụng khoá (chữ ký số, mã hoá,...).
- Public Key: Khoá công khai của chủ thể.
- Thumbrint Algorithm: Giải thuật hash dùng để tạo chuỗi băm cho khoá công khai.
- Thumbrint: Chuỗi băm tạo từ khoá công khai.

#### c) Sử dụng:
- Đảm bảo an toàn cho giao dịch trên nền web:
    - Dùng chứng chỉ số cho phép website chạy trên SSL (tối thiểu maúu chủ phải có chứng chỉ số): HTTP $\rightarrow$ HTTPS: Toàn bộ thông tin chuyển giữa server và client được đảm bảo tính bí mật (sử dụng mã hoá khoá đối xứng), toàn vẹn và xác thực (sử dụng hàm băm có khoá MAC/HMAC).
    - Chứng chỉ số để các bên xác thực thông tin nhận dạng của nhau.
- Chứng chỉ số có thể được dùng cho nhiều ứng dụng:
    - Email
    - FTP
    - ...

### 3. Hạ tầng khoá công khai - PKI (Public Key Infrastructure):
- Là một tập các phần cứng, phần mềm, nhân lực, chính sách và các thủ tục để tạo, quản lý, phân phối, sử dụng, lưu trữ và thu hồi các chứng chỉ số.
- Một PKI gồm:
    - Certificate Authority (CA): Cơ quan cấp và kiểm tra chứng chỉ số.
    - Registration Authority (RA): Bộ phận kiểm tra thông tin nhận dạng của user theo yêu cầu của CA.
    - Validation Authority (VA): Cơ quan xác nhận thông tin nhận dạng của user thay mặt CA.
    - Central Directory (CD): Là nơi lưu danh mục và lập chỉ số các khoá.
    - Certificate Management System: Hệ thống quản lý chứng chỉ.
    - Certficate Policy: Chính sách về chứng chỉ.
- Lưu đồ cấp và sử dụng:

![image](https://hackmd.io/_uploads/S1qCICtYWx.png)

## V. Các giao thức đảm bảo an toàn thông tin dựa trên mã hoá:
### 1. SSL/TLS (Secure Socket Layer/Transport Layer Security):
![image](https://hackmd.io/_uploads/ry2jKRYt-g.png)
![image](https://hackmd.io/_uploads/SJK3YAKYZg.png)
- SSL do côn ty Netscape phát minh năm 1993:
    - Các phiên bản: 1.0 (1993), 2.0 (1995), 3.0 (1996)
    - Hiện ít được dùng do nhiều lỗi và không được cập nhật.
- TLS được xây dựng vào năm 1999 dựa trên SSL 3.0 và do IETF phê chuẩn. Các phiên bản của TLS: 1.0 (1999), 1.1 (2005), 1.2 (2008), 1.3 (2015-draft).
- Đặc điểm:
    - Dùng mã hoá công khai để trao đổi khoá phiên. Mỗi khoá phiên chỉ được dùng trong một phiên làm việc.
    - Dùng khoá phiên và mã hoá khoá bí mật để mã hoá toàn bộ dữ liệu trao đổi.
    - Dùng hàm băm có khoá (MAC) để đảm bảo tính toàn vẹn và xác thực thông điệp.
    - Ít nhất một thực thể (thường là server) phải có chứng chỉ số cho khoá công khai (Public Key Certificate).
- Các giao thức con:

![image](https://hackmd.io/_uploads/S1489RFKZx.png)
    - SSL Handshake Protocol: Giao thức bắt tay của SSL, có nhiệm vụ trao đổi các thông điệp xác thực thực thể và thiết lập các thông số cho phiên làm việc.
    ![image](https://hackmd.io/_uploads/Hy_35CKFWg.png)
    - SSL Change Spec Protocol: Giao thức thiết lập việc sử dụng các bộ mã hoá được hỗ trợ bởi cả hai bên truyền thông.
    - SSL Alert Protocol: Giao thức cảnh báo của SSL.
    - SSL Record Protocol: Giao thức truyền các bản ghi của SSL có nhiệm vụ tạo đường hầm an toàn để chuyển thông tin đảm bảo tính bí mật, toàn vẹn và xác thực.
    ![image](https://hackmd.io/_uploads/rkYCqRYFWl.png)

### 2. SET (Secure Electronic Transactions):
![image](https://hackmd.io/_uploads/HJ9vjCtt-x.png)
- Là giao thức cho phép thanh toán điện tử an toàn bằng cách dùng thẻ tín dụng do hai công ty Visa International và MasterCard phát triển.
- Có khả năng đảm bảo các thuộc tính sau của thông tin truyền:
    - Bí mật thông tin.
    - Toàn vẹn thông tin.
    - Xác thực tài khoản chủ thẻ.
    - Xác thực nhà cung cấp.

### 3. PGP (Pretty Good Privacy):
![image](https://hackmd.io/_uploads/r1XynAYFZx.png)
- Do Philip Zimmermann phát triển năm 1991:
    - Cung cấp tính riêng tư.
    - Cung cấp tính xác thực.
- Được dùng rộng rãi và đã được thừa nhận thành chuẩn (RFC 3156).
- Cho phép:
    - Mã hoá dữ liệu bằng cách dùng mã hoá khoá bí mật và khoá công khai.
    - Tạo và kiểm tra chữ ký điện tử.

![image](https://hackmd.io/_uploads/BkgW3RKFbl.png)
![image](https://hackmd.io/_uploads/H1dmhAtt-x.png)
![image](https://hackmd.io/_uploads/ByUNhCtYbl.png)
- Mô hình trao đổi file đảm bảo tính bí mật và toàn vẹn sử dụng mã hoá khoá công khai và chữ ký số:

![image](https://hackmd.io/_uploads/Bku_3CFY-g.png)

### 4. IPSec (IP Security):
### 5. SSH (Secure Shell):
