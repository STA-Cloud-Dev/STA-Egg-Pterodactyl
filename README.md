# STA-Egg-Pterodactyl


## Danh mục

### AI

| Egg | Đường dẫn | Ghi chú |
| --- | --- | --- |
| OpenClaw | [`AI/OpenClaw.json`](AI/OpenClaw.json) | Chạy OpenClaw Gateway với persistent state trong `/home/container/.openclaw`. |

### Ngôn ngữ lập trình

| Egg | Đường dẫn | Ghi chú |
| --- | --- | --- |
| Bun Generic | [`code-languages/BunGeneric.json`](code-languages/BunGeneric.json) | Chạy ứng dụng JavaScript/TypeScript bằng Bun từ Git repo hoặc file upload. |
| C Generic | [`code-languages/CGeneric.json`](code-languages/CGeneric.json) | Chạy dự án .NET/C# từ Git repo hoặc file upload. |
| Golang Generic | [`code-languages/GolangGeneric.json`](code-languages/GolangGeneric.json) | Tải và build ứng dụng Go thành file thực thi. |
| Java Generic | [`code-languages/JavaGeneric.json`](code-languages/JavaGeneric.json) | Chạy ứng dụng Java từ file JAR, hỗ trợ Java 8 đến 25. |
| Nodejs Generic | [`code-languages/NodejsGeneric.json`](code-languages/NodejsGeneric.json) | Chạy ứng dụng JavaScript/TypeScript bằng nhiều phiên bản Node.js. |
| Python Generic | [`code-languages/PythonGeneric.json`](code-languages/PythonGeneric.json) | Chạy ứng dụng Python từ Git repo hoặc file upload, hỗ trợ Python 2.7 đến 3.15. |

### Linux

| Egg | Đường dẫn | Ghi chú |
| --- | --- | --- |
| STACloud Linux VPS | [`Linux/egg-linux.json`](Linux/egg-linux.json) | Linux VPS với SSH và tùy chọn giao diện VNC qua trình duyệt. |

### Minecraft

| Egg | Đường dẫn | Ghi chú |
| --- | --- | --- |
| BungeeCord | [`minecraft/egg-bungeecord.json`](minecraft/egg-bungeecord.json) | Proxy kết nối nhiều Minecraft server. |
| CanvasMC | [`minecraft/egg-canvas-mc.json`](minecraft/egg-canvas-mc.json) | Minecraft server với các tối ưu về tick, chunk và entity. |
| Fabric | [`minecraft/egg-fabric.json`](minecraft/egg-fabric.json) | Modding toolchain cho Minecraft 1.14 trở lên. |
| Folia | [`minecraft/egg-folia.json`](minecraft/egg-folia.json) | Fork của Paper với regionized multithreading. |
| Forge Enhanced | [`minecraft/egg-forge-enhanced.json`](minecraft/egg-forge-enhanced.json) | Minecraft Forge server với startup tùy biến. |
| Paper | [`minecraft/egg-paper.json`](minecraft/egg-paper.json) | Spigot fork hướng tới hiệu năng cao. |
| PocketMine-MP | [`minecraft/egg-pterodactyl-pocketmine-m-p.json`](minecraft/egg-pterodactyl-pocketmine-m-p.json) | Chạy PocketMine-MP cho Minecraft Bedrock. |
| Vanilla Bedrock | [`minecraft/egg-vanilla-bedrock.json`](minecraft/egg-vanilla-bedrock.json) | Minecraft Bedrock server chính chủ. |
| Vanilla Minecraft | [`minecraft/egg-vanilla-minecraft.json`](minecraft/egg-vanilla-minecraft.json) | Minecraft Java server chính chủ. |

### Proxy và voice server

| Egg | Đường dẫn | Ghi chú |
| --- | --- | --- |
| STAShield | [`Proxy/egg-stashield.json`](Proxy/egg-stashield.json) | Proxy bảo vệ Minecraft Java và forward traffic tới backend. |
| STA Cloud Velocity | [`Proxy/velocity.json`](Proxy/velocity.json) | Velocity proxy, hỗ trợ Java 8, 11, 17, 21 và 25. |
| LavaLink | [`voice-servers/LavaLink.json`](voice-servers/LavaLink.json) | Lavalink server, hỗ trợ Java 8, 11, 17, 21 và 25. |

## Cách cài đặt

1. Tải file JSON phù hợp từ repository.
2. Mở khu vực **Nests** trong Pterodactyl Admin Panel.
3. Chọn nest muốn dùng, mở menu **Import Egg** và tải file JSON lên.
4. Kiểm tra Docker image, startup command và các biến môi trường trước khi tạo server.
5. Tạo server, gán allocation và khởi động. Xem console để xác nhận quá trình install đã hoàn tất.

Nếu panel của bạn không có mục **Import Egg**, hãy tham khảo tài liệu của phiên bản panel đang sử dụng. Không sửa trực tiếp file egg sau khi import nếu không cần thiết; hãy cập nhật từ file JSON gốc để tránh sai lệch cấu hình.

## Lưu ý vận hành

- Đọc mô tả của từng biến môi trường trước khi thay đổi giá trị mặc định.
- Không commit token, mật khẩu SSH, bot token hoặc URL private vào egg.
- Với proxy, kiểm tra backend host, backend port và allocation trước khi public server.
- Với egg có script tải file từ Internet, nên pin version hoặc kiểm tra URL trước khi deploy production.
- Luôn backup dữ liệu server trước khi đổi egg, Docker image hoặc startup command.

## Đóng góp

1. Tạo branch cho thay đổi của bạn.
2. Sửa file JSON đúng định dạng `PTDL_v2`, giữ nguyên tên biến môi trường hiện có nếu không có lý do bắt buộc.
3. Kiểm tra JSON hợp lệ và thử install/start trên một server test.
4. Mở pull request, mô tả rõ thay đổi, image yêu cầu và cách kiểm thử.

## Giấy phép và nguồn

Khi sử dụng egg có nguồn từ dự án bên ngoài, hãy giữ lại thông tin tác giả và tuân thủ giấy phép của dự án đó. Các egg trong repository có thể có yêu cầu riêng được ghi trong trường `author`, `description` hoặc comment của file.

## Liên hệ

- Email: `stacloud.dev@gmail.com`
- Tổ chức: [STA Cloud Dev](https://github.com/STA-Cloud-Dev)
