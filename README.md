# STA Egg Pterodactyl

Bộ **Egg Pterodactyl** do [STA Cloud Dev](https://github.com/STA-Cloud-Dev) phát triển và duy trì. Repository tập trung vào các template sẵn sàng import cho Minecraft, proxy, voice server, PHP và các ứng dụng chạy bằng ngôn ngữ lập trình phổ biến.

> **Định dạng:** `PTDL_v2`
> **Tác giả mặc định:** `stacloud.dev@gmail.com`

## Mục lục

- [Danh mục Egg](#danh-mục-egg)
- [Cài đặt](#cài-đặt)
- [Sau khi import](#sau-khi-import)
- [Lưu ý bảo mật và vận hành](#lưu-ý-bảo-mật-và-vận-hành)
- [Đóng góp](#đóng-góp)
- [Giấy phép và nguồn](#giấy-phép-và-nguồn)
- [Liên hệ](#liên-hệ)

## Danh mục Egg

### Ngôn ngữ lập trình

| Egg | Tệp | Mô tả |
| --- | --- | --- |
| Bun Generic | [`code-languages/BunGeneric.json`](code-languages/BunGeneric.json) | Chạy ứng dụng JavaScript/TypeScript bằng Bun từ Git repository hoặc file upload. |
| C Generic | [`code-languages/CGeneric.json`](code-languages/CGeneric.json) | Chạy dự án C#/.NET với các phiên bản .NET LTS được hỗ trợ. |
| Golang Generic | [`code-languages/GolangGeneric.json`](code-languages/GolangGeneric.json) | Tải mã nguồn và build ứng dụng Go thành file thực thi. |
| Java Generic | [`code-languages/JavaGeneric.json`](code-languages/JavaGeneric.json) | Chạy ứng dụng Java từ file JAR với nhiều phiên bản Java. |
| Node.js Generic | [`code-languages/NodejsGeneric.json`](code-languages/NodejsGeneric.json) | Chạy ứng dụng JavaScript/TypeScript bằng nhiều phiên bản Node.js. |
| Python Generic | [`code-languages/PythonGeneric.json`](code-languages/PythonGeneric.json) | Chạy ứng dụng Python từ Git repository hoặc file upload. |

### PHP và Web

| Egg | Tệp | Mô tả |
| --- | --- | --- |
| STACloud PHP Web | [`Web/PHPweb.json`](Web/PHPweb.json) | Hosting PHP generic, hỗ trợ PHP 5.6 đến 8.5. Các phiên bản EOL chỉ nên dùng cho mục đích migration cô lập. |

### Minecraft

| Egg | Tệp | Mô tả |
| --- | --- | --- |
| BungeeCord | [`minecraft/egg-bungeecord.json`](minecraft/egg-bungeecord.json) | Proxy kết nối nhiều Minecraft server. |
| CanvasMC | [`minecraft/egg-canvas-mc.json`](minecraft/egg-canvas-mc.json) | Minecraft server với các tối ưu cho tick, chunk và entity. |
| Fabric | [`minecraft/egg-fabric.json`](minecraft/egg-fabric.json) | Modding toolchain cho Minecraft 1.14 trở lên. |
| Folia | [`minecraft/egg-folia.json`](minecraft/egg-folia.json) | Fork của Paper với regionized multithreading. |
| Forge Enhanced | [`minecraft/egg-forge-enhanced.json`](minecraft/egg-forge-enhanced.json) | Minecraft Forge server với startup có thể tùy biến. |
| Paper | [`minecraft/egg-paper.json`](minecraft/egg-paper.json) | Spigot fork hướng tới hiệu năng cao. |
| PocketMine-MP | [`minecraft/egg-pterodactyl-pocketmine-m-p.json`](minecraft/egg-pterodactyl-pocketmine-m-p.json) | Chạy PocketMine-MP cho Minecraft Bedrock. |
| Vanilla Bedrock | [`minecraft/egg-vanilla-bedrock.json`](minecraft/egg-vanilla-bedrock.json) | Minecraft Bedrock server chính chủ. |
| Vanilla Minecraft | [`minecraft/egg-vanilla-minecraft.json`](minecraft/egg-vanilla-minecraft.json) | Minecraft Java server chính chủ. |

### Proxy và Voice Server

| Egg | Tệp | Mô tả |
| --- | --- | --- |
| STAShield | [`Proxy/egg-stashield.json`](Proxy/egg-stashield.json) | Proxy bảo vệ Minecraft Java và chuyển tiếp traffic tới backend. |
| STA Cloud Velocity | [`Proxy/velocity.json`](Proxy/velocity.json) | Velocity proxy, hỗ trợ Java 8, 11, 17, 21 và 25. |
| LavaLink | [`voice-servers/LavaLink.json`](voice-servers/LavaLink.json) | Lavalink server, hỗ trợ Java 8, 11, 17, 21 và 25. |

## Cài đặt

### Import qua Admin Panel

1. Tải file `.json` tương ứng từ repository.
2. Đăng nhập **Pterodactyl Admin Panel**.
3. Mở **Nests**, chọn nest cần dùng hoặc tạo nest mới.
4. Chọn **Import Egg**, tải file JSON lên và xác nhận import.
5. Kiểm tra lại Docker image, startup command và các biến môi trường.
6. Tạo server, chọn egg vừa import, gán allocation rồi khởi động server.

Nếu panel không hiển thị **Import Egg**, hãy kiểm tra quyền administrator và tài liệu của phiên bản Pterodactyl đang sử dụng.

### Cập nhật Egg

- So sánh file JSON mới với phiên bản đang sử dụng trước khi import lại.
- Backup dữ liệu server và ghi chú các biến môi trường đã tùy chỉnh.
- Không chỉnh sửa file egg gốc nếu không cần thiết; ưu tiên cập nhật từ repository để tránh cấu hình bị lệch.

## Sau khi import

Trước khi đưa server vào sử dụng, hãy kiểm tra:

- Docker image có tồn tại và tương thích với phiên bản ứng dụng.
- Startup command và đường dẫn file dự án/JAR là chính xác.
- Các biến môi trường bắt buộc đã được cấu hình.
- Allocation, port backend và địa chỉ kết nối phù hợp với mô hình triển khai.
- Installation script hoàn tất thành công trong console.

## Lưu ý bảo mật và vận hành

- Không commit token, mật khẩu, SSH key, bot token hoặc URL private vào file egg.
- Chỉ dùng image và URL tải xuống từ nguồn tin cậy; nên pin version khi triển khai production.
- Các phiên bản runtime đã **EOL** chỉ nên dùng tạm thời cho migration hoặc hệ thống cô lập.
- Với proxy, kiểm tra kỹ backend host, backend port, allocation và firewall trước khi public server.
- Backup dữ liệu trước khi đổi egg, Docker image, startup command hoặc runtime.
- Đọc mô tả của từng biến môi trường trước khi thay đổi giá trị mặc định.

## Đóng góp

1. Tạo branch riêng cho thay đổi.
2. Chỉnh sửa đúng định dạng `PTDL_v2` và giữ nguyên tên biến môi trường hiện có nếu không có lý do bắt buộc.
3. Kiểm tra JSON hợp lệ và thử install/start trên server test.
4. Mở pull request, mô tả rõ thay đổi, image yêu cầu và kết quả kiểm thử.

## Giấy phép và nguồn

Một số egg có thể sử dụng image, script hoặc thành phần từ dự án bên ngoài. Khi sử dụng hoặc phân phối lại, hãy:

- Giữ lại thông tin tác giả và ghi chú nguồn.
- Tuân thủ giấy phép của dự án liên quan.
- Kiểm tra các trường `author`, `description` và comment trong từng file JSON.

## Liên hệ

- Email: [`stacloud.dev@gmail.com`](mailto:stacloud.dev@gmail.com)
- Tổ chức: [STA Cloud Dev](https://github.com/STA-Cloud-Dev)
