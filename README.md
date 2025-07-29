# Terminology

## 1. Thuật ngữ phân tích mã độc / reverse engineering.

| Thuật ngữ         | Diễn giải ngắn                                          |
| ----------------- | ------------------------------------------------------- |
| **Dropper**       | Mã thực thi đầu tiên dùng để thả malware chính          |
| **Loader**        | Thành phần tải và thực thi mã độc vào bộ nhớ            |
| **Payload**       | Phần mã độc chính gây ra tác động (backdoor, shell,...) |
| **Stub**          | Phần mã nhỏ để đánh lừa phân tích, giải mã payload      |
| **Obfuscation**   | Kỹ thuật làm rối mã để tránh phân tích                  |
| **Packer**        | Công cụ nén và mã hóa binary để che giấu payload        |
| **Unpacking**     | Quá trình giải nén/mở mã đã bị đóng gói                 |
| **Deobfuscation** | Quá trình gỡ rối mã độc đã bị làm rối                   |


## 2. Phân tích mã nguồn / Static Analysis.

| Thuật ngữ          | Diễn giải                                                        |
| ------------------ | ---------------------------------------------------------------- |
| **Source**         | Điểm vào dữ liệu không tin cậy (input từ user, network, file...) |
| **Sink**           | Điểm sử dụng dữ liệu có thể gây hại nếu không kiểm tra           |
| **Sanitizer**      | Hàm làm sạch/kiểm tra dữ liệu trước khi đến sink                 |
| **Path**           | Đường đi của dữ liệu từ source → sink                            |
| **Taint Analysis** | Phân tích xem dữ liệu từ source có chảy đến sink không           |
| **Control Flow**   | Luồng điều khiển chương trình (if, loop, call,...)               |
| **Data Flow**      | Luồng dữ liệu trong chương trình                                 |

## 3. Vulnerability Research / Exploit Development.

| Thuật ngữ                             | Diễn giải                                                      |
| ------------------------------------- | -------------------------------------------------------------- |
| **Bug Class**                         | Loại lỗi (buffer overflow, use-after-free, race condition,...) |
| **Root Cause**                        | Nguyên nhân sâu xa của bug                                     |
| **PoC (Proof of Concept)**            | Mã khai thác thử nghiệm lỗi                                    |
| **Exploit Chain**                     | Chuỗi các kỹ thuật nối nhau để chiếm quyền kiểm soát hệ thống  |
| **Primitives**                        | Kỹ thuật cơ bản trong khai thác (read/write primitive,...)     |
| **ROP (Return Oriented Programming)** | Kỹ thuật bypass DEP/ASLR dùng gadget nhỏ                       |
| **Gadget**                            | Đoạn mã nhỏ có thể tận dụng trong ROP chain                    |
| **Shellcode**                         | Mã máy nhỏ, thường dùng để mở shell hoặc kết nối về máy chủ    |


## 4. Runtime / Dynamic Analysis

| Thuật ngữ           | Diễn giải                                                    |
| ------------------- | ------------------------------------------------------------ |
| **Instrumentation** | Thêm mã/hook để quan sát hoặc kiểm soát runtime              |
| **Hooking**         | Can thiệp vào API hoặc hàm để theo dõi hoặc thay đổi hành vi |
| **Tracing**         | Theo dõi luồng gọi hàm và hoạt động                          |
| **Sandbox**         | Môi trường cách ly an toàn để chạy thử malware/code          |
| **Debugger**        | Công cụ dừng chương trình và quan sát trạng thái             |
| **Break Point**     | Điểm dừng được cài đặt trong debugger                        |


## 5. Security Intelligence / Phân tích chiến dịch.

| Thuật ngữ                                 | Diễn giải                                  |
| ----------------------------------------- | ------------------------------------------ |
| **IOC (Indicator of Compromise)**         | Dấu hiệu nhận biết hệ thống đã bị xâm nhập |
| **TTP (Tactics, Techniques, Procedures)** | Mô hình tấn công của nhóm APT              |
| **Campaign**                              | Một chuỗi tấn công kéo dài có chủ đích     |
| **Attribution**                           | Truy dấu nhóm đứng sau tấn công            |
| **C2 (Command and Control)**              | Server điều khiển malware sau khi nhiễm    |


## 6. Các thuật ngữ chung khác.

| Thuật ngữ             | Diễn giải                                                     |
| --------------------- | ------------------------------------------------------------- |
| **Zero-Day**          | Lỗi chưa được công bố/vá, nguy hiểm cao                       |
| **Patch Diffing**     | So sánh bản vá để tìm điểm thay đổi và khai thác              |
| **Fuzzing**           | Kỹ thuật tự động tìm bug bằng cách gửi input ngẫu nhiên       |
| **Crash Triage**      | Phân loại lỗi sau khi fuzz để xem có thể khai thác được không |
| **Memory Corruption** | Lỗi thao tác bộ nhớ gây ra hành vi bất thường                 |

## 7. Exploit Internals / Kỹ thuật khai thác nâng cao.

| Thuật ngữ                                           | Diễn giải ngắn gọn                                               |
| --------------------------------------------------- | ---------------------------------------------------------------- |
| **ASLR (Address Space Layout Randomization)**       | Cơ chế ngẫu nhiên hóa vị trí bộ nhớ để chống khai thác           |
| **DEP/NX (Data Execution Prevention / No eXecute)** | Chống thực thi code trong vùng dữ liệu                           |
| **Stack Pivoting**                                  | Thay đổi con trỏ stack để chuyển hướng kiểm soát                 |
| **Heap Spray**                                      | Lấp đầy heap với shellcode nhằm tăng xác suất khai thác          |
| **Type Confusion**                                  | Sử dụng đối tượng sai kiểu gây lỗi logic hoặc memory corruption  |
| **Use-After-Free (UAF)**                            | Truy cập vùng nhớ đã bị giải phóng                               |
| **Double Free**                                     | Giải phóng 1 vùng nhớ 2 lần dẫn đến corruption                   |
| **Integer Overflow**                                | Tràn số dẫn đến bypass kiểm tra hoặc ghi đè bộ nhớ               |
| **Race Condition**                                  | Lỗi do hai tiến trình truy cập dữ liệu đồng thời không đúng cách |


## 8. Symbolic Execution / Program Analysis.

| Thuật ngữ                          | Diễn giải                                                       |
| ---------------------------------- | --------------------------------------------------------------- |
| **SMT Solver**                     | Bộ giải logic được dùng trong symbolic execution (Z3, STP)      |
| **CFG (Control Flow Graph)**       | Đồ thị biểu diễn các luồng điều khiển trong chương trình        |
| **Dominator Tree**                 | Cấu trúc xác định điểm kiểm soát trong CFG                      |
| **SSA (Static Single Assignment)** | Biểu diễn mỗi biến được gán giá trị đúng 1 lần                  |
| **Alias Analysis**                 | Phân tích xem 2 biến có trỏ cùng địa chỉ không                  |
| **Interprocedural Analysis**       | Phân tích luồng dữ liệu giữa các hàm hoặc module                |
| **Intra-procedural**               | Phân tích bên trong một hàm duy nhất                            |
| **Loop Unrolling**                 | Kỹ thuật tối ưu hóa/phân tích vòng lặp bằng cách "mở rộng" vòng |

## 9. Binary Reversing / ELF, PE, Mach-O Structures.

| Thuật ngữ                                | Diễn giải                                               |
| ---------------------------------------- | ------------------------------------------------------- |
| **Import Address Table (IAT)**           | Bảng chứa địa chỉ các API được import (Windows PE)      |
| **Export Table**                         | Bảng mô tả các hàm được export ra ngoài                 |
| **Entry Point**                          | Điểm đầu tiên được thực thi khi file chạy               |
| **Section (.text, .data, .rdata, .bss)** | Các vùng chức năng khác nhau trong file thực thi        |
| **Relocation**                           | Cơ chế cập nhật địa chỉ khi load binary                 |
| **Thunk**                                | Hàm nhỏ chuyển hướng gọi API, thường thấy trong hooking |
| **Syscall Stub**                         | Mã máy gọi syscall trực tiếp (thường bypass AV/EDR)     |
| **Symbol Table**                         | Danh sách tên biến/hàm còn giữ lại trong binary (ELF)   |
| **DWARF Debug Info**                     | Dữ liệu debug giữ thông tin như tên hàm, biến,...       |

## 10. Threat Hunting / APT Analysis.

| Thuật ngữ                      | Diễn giải                                                                                |
| ------------------------------ | ---------------------------------------------------------------------------------------- |
| **YARA Rules**                 | Tập luật để xác định malware dựa trên pattern                                            |
| **Mutex (Mutual Exclusion)**   | Dấu hiệu dùng để tránh chạy trùng malware                                                |
| **Beaconing**                  | Hành vi kết nối định kỳ về server C2                                                     |
| **Lateral Movement**           | Di chuyển bên trong hệ thống sau khi xâm nhập                                            |
| **Persistence Mechanism**      | Cách malware bám trụ qua reboot (registry, startup, services)                            |
| **Exfiltration**               | Hành vi trộm và gửi dữ liệu ra ngoài                                                     |
| **Living off the Land (LotL)** | Sử dụng công cụ sẵn có trong hệ thống (PowerShell, certutil, wmic...) để tránh phát hiện |
| **DLL Sideloading**            | Tải một DLL giả mạo cùng tên vào quá trình hợp pháp                                      |
| **Code Injection**             | Nhúng mã độc vào tiến trình khác (CreateRemoteThread, APC, v.v.)                         |

## 11. Phân tích & viết mã shellcode.

| Thuật ngữ                  | Diễn giải                                             |
| -------------------------- | ----------------------------------------------------- |
| **Syscall Table**          | Danh sách số hiệu hệ thống (syscall ID) theo từng OS  |
| **Egg Hunter**             | Shellcode nhỏ đi tìm shellcode lớn trong memory       |
| **Stager / Stage 1**       | Mã nhỏ dùng để tải payload chính (stage 2)            |
| **Null-Free Shellcode**    | Shellcode không có byte null (`0x00`) để tránh bị cắt |
| **Polymorphic Shellcode**  | Shellcode tự thay đổi mã để tránh bị phát hiện        |
| **Encoder / Decoder Stub** | Dùng để bypass AV bằng cách mã hóa shellcode          |



