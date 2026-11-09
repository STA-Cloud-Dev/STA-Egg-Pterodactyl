# STA Egg Pterodactyl

Bộ **Egg Pterodactyl** do [STA Cloud Dev](https://github.com/STA-Cloud-Dev) phát triển và duy trì. Các template được thiết kế để import trực tiếp vào Pterodactyl, phục vụ nhiều nhu cầu từ website, ứng dụng lập trình, AI đến Minecraft và proxy.

<p align="center">
  <strong>23 Egg</strong> · <strong>6 nhóm</strong> · <code>PTDL_v2</code>
</p>

## Mục lục

- [Tổng quan](#tổng-quan)
- [Danh mục Egg](#danh-mục-egg)
- [Cài đặt](#cài-đặt)
- [Kiểm tra sau khi import](#kiểm-tra-sau-khi-import)
- [Cập nhật Egg](#cập-nhật-egg)
- [Lưu ý bảo mật và vận hành](#lưu-ý-bảo-mật-và-vận-hành)
- [Đóng góp](#đóng-góp)
- [Giấy phép và nguồn](#giấy-phép-và-nguồn)
- [Liên hệ](#liên-hệ)

## Tổng quan

| Nhóm | Số lượng | Nội dung |
| --- | :---: | --- |
| AI | 1 | OpenClaw Gateway |
| Ngôn ngữ lập trình | 6 | Bun, C#/.NET, Go, Java, Node.js và Python |
| PHP và Web | 4 | PHP Web, Laravel, WordPress và phpMyAdmin |
| Minecraft | 9 | Vanilla, Paper, Fabric, Forge, Folia, CanvasMC và proxy |
| Proxy | 2 | STAShield và Velocity |
| Voice Server | 1 | LavaLink |

## Danh mục Egg

### AI

| Egg | Tệp | Runtime / ghi chú |
| --- | --- | --- |
| OpenClaw | [`AI/OpenClaw.json`](AI/OpenClaw.json) | Chạy OpenClaw Gateway với persistent state tại `/home/container/.openclaw`. |

### Ngôn ngữ lập trình

| Egg | Tệp | Runtime / ghi chú |
| --- | --- | --- |
| Bun Generic | [`code-languages/BunGeneric.json`](code-languages/BunGeneric.json) | Bun stable mới nhất; chạy JavaScript/TypeScript từ Git repository hoặc file upload. |
| C Generic | [`code-languages/CGeneric.json`](code-languages/CGeneric.json) | .NET 8 và .NET 10; chạy dự án C# từ Git repository hoặc file upload. |
| Golang Generic | [`code-languages/GolangGeneric.json`](code-languages/GolangGeneric.json) | Go 1.24, 1.26 và 1.27; tải, build và chạy ứng dụng Go. |
| Java Generic | [`code-languages/JavaGeneric.json`](code-languages/JavaGeneric.json) | Java 8, 11, 17, 21 và 25; chạy ứng dụng từ file JAR. |
| Node.js Generic | [`code-languages/NodejsGeneric.json`](code-languages/NodejsGeneric.json) | Node.js 22, 24 và 26; chạy ứng dụng JavaScript/TypeScript. |
| Python Generic | [`code-languages/PythonGeneric.json`](code-languages/PythonGeneric.json) | Python 3.10 đến 3.14; chạy ứng dụng từ Git repository hoặc file upload. |

### PHP và Web

| Egg | Tệp | Runtime / ghi chú |
| --- | --- | --- |
| STACloud PHP Web | [`Web/PHPweb.json`](Web/PHPweb.json) | Hosting PHP generic, hỗ trợ PHP 5.6 đến 8.5. |
| STACloud Laravel | [`Web/Laravel.json`](Web/Laravel.json) | Laravel 12/13, Composer và public web root; hỗ trợ PHP 8.3 đến 8.5. |
| STACloud WordPress | [`Web/WordPress.json`](Web/WordPress.json) | Tự động cài WordPress, hỗ trợ PHP 8.2 đến 8.5. |
| STACloud phpMyAdmin | [`Web/phpMyAdmin.json`](Web/phpMyAdmin.json) | phpMyAdmin standalone tại `/`, hỗ trợ kết nối database và PHP 5.6 đến 8.5. |

### Minecraft

| Egg | Tệp | Runtime / ghi chú |
| --- | --- | --- |
| BungeeCord | [`minecraft/egg-bungeecord.json`](minecraft/egg-bungeecord.json) | Proxy kết nối nhiều Minecraft server. |
| CanvasMC | [`minecraft/egg-canvas-mc.json`](minecraft/egg-canvas-mc.json) | Tối ưu tick dimension, chunk generation và entity handling. |
| Fabric | [`minecraft/egg-fabric.json`](minecraft/egg-fabric.json) | Modding toolchain cho Minecraft 1.14 trở lên, bao gồm cả snapshot. |
| Folia | [`minecraft/egg-folia.json`](minecraft/egg-folia.json) | Paper fork với regionized multithreading. |
| Forge Enhanced | [`minecraft/egg-forge-enhanced.json`](minecraft/egg-forge-enhanced.json) | Minecraft Forge server cho mod và modpack. |
| Paper | [`minecraft/egg-paper.json`](minecraft/egg-paper.json) | Spigot fork hướng tới hiệu năng cao. |
| PocketMine-MP | [`minecraft/egg-pterodactyl-pocketmine-m-p.json`](minecraft/egg-pterodactyl-pocketmine-m-p.json) | Minecraft Bedrock server chạy bằng PocketMine-MP. |
| Vanilla Bedrock | [`minecraft/egg-vanilla-bedrock.json`](minecraft/egg-vanilla-bedrock.json) | Minecraft Bedrock server chính chủ. |
| Vanilla Minecraft | [`minecraft/egg-vanilla-minecraft.json`](minecraft/egg-vanilla-minecraft.json) | Minecraft Java server chính chủ. |

### Proxy và Voice Server

| Egg | Tệp | Runtime / ghi chú |
| --- | --- | --- |
| STAShield | [`Proxy/egg-stashield.json`](Proxy/egg-stashield.json) | Proxy bảo vệ Minecraft Java và chuyển tiếp traffic tới backend. |
| STA Cloud Velocity | [`Proxy/velocity.json`](Proxy/velocity.json) | Velocity proxy với Java 8, 11, 17, 21 và 25. |
| LavaLink | [`voice-servers/LavaLink.json`](voice-servers/LavaLink.json) | Lavalink server với Java 8, 11, 17, 21 và 25. |

## Cài đặt

### Import qua Admin Panel

1. Tải file `.json` phù hợp từ repository.
2. Đăng nhập **Pterodactyl Admin Panel** bằng tài khoản administrator.
3. Mở **Nests**, chọn nest cần dùng hoặc tạo nest mới.
4. Chọn **Import Egg**, tải file JSON lên và xác nhận import.
5. Kiểm tra Docker image, startup command và các biến môi trường.
6. Tạo server, chọn Egg vừa import, gán allocation rồi khởi động.

Nếu panel không có mục **Import Egg**, hãy kiểm tra quyền administrator và tài liệu của phiên bản Pterodactyl đang sử dụng.

## Kiểm tra sau khi import

Trước khi đưa server vào sử dụng, hãy xác nhận:

- Docker image tồn tại và tương thích với runtime đã chọn.
- Các biến môi trường bắt buộc đã được cấu hình đúng.
- Startup command và đường dẫn dự án/JAR chính xác.
- Allocation, port backend, database host và firewall phù hợp với mô hình triển khai.
- Installation script hoàn tất thành công trong console.
- Website hoặc dịch vụ chỉ public sau khi đã kiểm tra đăng nhập, health check và log.

## Cập nhật Egg

- Backup dữ liệu server trước khi đổi Egg, image hoặc startup command.
- Ghi chú các biến môi trường đã tùy chỉnh trước khi import phiên bản mới.
- So sánh file JSON mới với cấu hình hiện tại để tránh mất thay đổi quan trọng.
- Không sửa trực tiếp file Egg gốc nếu không cần thiết; ưu tiên cập nhật từ repository.
- Với runtime hoặc package EOL, chỉ sử dụng cho migration hoặc hệ thống cô lập và lên kế hoạch nâng cấp.

## Lưu ý bảo mật và vận hành

- Không commit token, mật khẩu, SSH key, bot token hoặc URL private vào file Egg.
- Chỉ dùng Docker image và URL tải xuống từ nguồn tin cậy; nên pin version khi triển khai production.
- Với STAShield, Velocity và các proxy Minecraft, kiểm tra kỹ backend host, backend port, allocation và firewall.
- Với phpMyAdmin, giới hạn truy cập bằng firewall, reverse proxy hoặc VPN; không public trực tiếp nếu không cần thiết.
- Đọc mô tả của từng biến môi trường trước khi thay đổi giá trị mặc định.
- Theo dõi log cài đặt và log runtime sau mỗi lần thay đổi cấu hình.

## Đóng góp

1. Tạo branch riêng cho thay đổi.
2. Chỉnh sửa đúng định dạng `PTDL_v2`, giữ nguyên tên biến môi trường hiện có nếu không có lý do bắt buộc.
3. Kiểm tra JSON hợp lệ và thử install/start trên server test.
4. Mở pull request, mô tả rõ thay đổi, image yêu cầu và kết quả kiểm thử.

## Giấy phép và nguồn

Một số Egg có thể sử dụng image, script hoặc thành phần từ dự án bên ngoài. Khi sử dụng hoặc phân phối lại:

- Giữ lại thông tin tác giả và ghi chú nguồn.
- Tuân thủ giấy phép của dự án liên quan.
- Kiểm tra các trường `author`, `description` và comment trong từng file JSON.

## Liên hệ

- Email: [`stacloud.dev@gmail.com`](mailto:stacloud.dev@gmail.com)
- Tổ chức: [STA Cloud Dev](https://github.com/STA-Cloud-Dev)
