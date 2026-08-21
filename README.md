# STA-Egg-Pterodactyl

Bo suu tap egg cho Pterodactyl va Pelican, duoc duy tri boi STACloud. Cac egg duoc dong goi theo dinh dang `PTDL_v2` va co the import truc tiep vao node hoac panel.

## Danh muc

### AI

| Egg | Duong dan | Ghi chu |
| --- | --- | --- |
| OpenClaw | [`AI/OpenClaw.json`](AI/OpenClaw.json) | Chay OpenClaw Gateway voi persistent state trong `/home/container/.openclaw`. |

### Ngon ngu lap trinh

| Egg | Duong dan | Ghi chu |
| --- | --- | --- |
| Bun Generic | [`code-languages/BunGeneric.json`](code-languages/BunGeneric.json) | Chay ung dung JavaScript/TypeScript bang Bun tu Git repo hoac file upload. |
| C Generic | [`code-languages/CGeneric.json`](code-languages/CGeneric.json) | Chay du an .NET/C# tu Git repo hoac file upload. |
| Golang Generic | [`code-languages/GolangGeneric.json`](code-languages/GolangGeneric.json) | Tai va build ung dung Go thanh file thuc thi. |
| Java Generic | [`code-languages/JavaGeneric.json`](code-languages/JavaGeneric.json) | Chay ung dung Java tu file JAR, ho tro Java 8 den 25. |
| Nodejs Generic | [`code-languages/NodejsGeneric.json`](code-languages/NodejsGeneric.json) | Chay ung dung JavaScript/TypeScript bang nhieu phien ban Node.js. |
| Python Generic | [`code-languages/PythonGeneric.json`](code-languages/PythonGeneric.json) | Chay ung dung Python tu Git repo hoac file upload, ho tro Python 2.7 den 3.15. |

### Linux

| Egg | Duong dan | Ghi chu |
| --- | --- | --- |
| STACloud Linux VPS | [`Linux/egg-linux.json`](Linux/egg-linux.json) | Linux VPS voi SSH va tuy chon giao dien VNC qua trinh duyet. |

### Minecraft

| Egg | Duong dan | Ghi chu |
| --- | --- | --- |
| BungeeCord | [`minecraft/egg-bungeecord.json`](minecraft/egg-bungeecord.json) | Proxy ket noi nhieu Minecraft server. |
| CanvasMC | [`minecraft/egg-canvas-mc.json`](minecraft/egg-canvas-mc.json) | Minecraft server voi cac toi uu ve tick, chunk va entity. |
| Fabric | [`minecraft/egg-fabric.json`](minecraft/egg-fabric.json) | Modding toolchain cho Minecraft 1.14 tro len. |
| Folia | [`minecraft/egg-folia.json`](minecraft/egg-folia.json) | Fork cua Paper voi regionized multithreading. |
| Forge Enhanced | [`minecraft/egg-forge-enhanced.json`](minecraft/egg-forge-enhanced.json) | Minecraft Forge server voi startup tuy bien. |
| Paper | [`minecraft/egg-paper.json`](minecraft/egg-paper.json) | Spigot fork huong toi hieu nang cao. |
| PocketMine-MP | [`minecraft/egg-pterodactyl-pocketmine-m-p.json`](minecraft/egg-pterodactyl-pocketmine-m-p.json) | Chay PocketMine-MP cho Minecraft Bedrock. |
| Vanilla Bedrock | [`minecraft/egg-vanilla-bedrock.json`](minecraft/egg-vanilla-bedrock.json) | Minecraft Bedrock server chinh chu. |
| Vanilla Minecraft | [`minecraft/egg-vanilla-minecraft.json`](minecraft/egg-vanilla-minecraft.json) | Minecraft Java server chinh chu. |

### Proxy va voice server

| Egg | Duong dan | Ghi chu |
| --- | --- | --- |
| STAShield | [`Proxy/egg-stashield.json`](Proxy/egg-stashield.json) | Proxy bao ve Minecraft Java va forward traffic toi backend. |
| STA Cloud Velocity | [`Proxy/velocity.json`](Proxy/velocity.json) | Velocity proxy, ho tro Java 8, 11, 17, 21 va 25. |
| LavaLink | [`voice-servers/LavaLink.json`](voice-servers/LavaLink.json) | Lavalink server, ho tro Java 8, 11, 17, 21 va 25. |

## Cach cai dat

1. Tai file JSON phu hop tu repository.
2. Mo khu vuc **Nests** trong Pterodactyl Admin Panel.
3. Chon nest muon dung, mo menu **Import Egg** va tai file JSON len.
4. Kiem tra Docker image, startup command va cac bien moi truong truoc khi tao server.
5. Tao server, gan allocation va khoi dong. Xem console de xac nhan qua trinh install da hoan tat.

Neu panel cua ban khong co muc **Import Egg**, hay tham khao tai lieu cua phien ban panel dang su dung. Khong sua truc tiep file egg sau khi import neu khong can thiet; hay cap nhat tu file JSON goc de tranh sai lech cau hinh.

## Luu y van hanh

- Doc mo ta cua tung bien moi truong truoc khi thay doi gia tri mac dinh.
- Khong commit token, mat khau SSH, bot token hoac URL private vao egg.
- Voi proxy, kiem tra backend host, backend port va allocation truoc khi public server.
- Voi egg co script tai file tu Internet, nen pin version hoac kiem tra URL truoc khi deploy production.
- Luon backup du lieu server truoc khi doi egg, Docker image hoac startup command.

## Dong gop

1. Tao branch cho thay doi cua ban.
2. Sua file JSON dung dinh dang `PTDL_v2`, giu nguyen ten bien moi truong hien co neu khong co ly do bat buoc.
3. Kiem tra JSON hop le va thu install/start tren mot server test.
4. Mo pull request, mo ta ro thay doi, image yeu cau va cach kiem thu.

## Giay phep va nguon

Khi su dung egg co nguon tu du an ben ngoai, hay giu lai thong tin tac gia va tuan thu giay phep cua du an do. Cac egg trong repository co the co yeu cau rieng duoc ghi trong truong `author`, `description` hoac comment cua file.

## Lien he

- Email: `stacloud.dev@gmail.com`
- To chuc: [STA Cloud Dev](https://github.com/STA-Cloud-Dev)