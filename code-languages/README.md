# STA Cloud Code Languages

Bộ egg riêng của STA Cloud, định dạng `PTDL_v2`. Các file JSON trong thư mục này là file import vào Panel.

## Phiên bản và image

Danh mục được đối chiếu nguồn upstream ngày 23/11/2026. Nhãn `Legacy/EOL` chỉ dành cho tương thích ứng dụng cũ; không phải bản khuyến nghị. Không bao gồm preview/canary hoặc mọi bản lịch sử.

| Egg | Phiên bản | Tag image (`ghcr.io/sta-cloud-dev/deverlopment:`) |
| --- | --- | --- |
| [STA Cloud \| Bun](BunGeneric.json) | Bun Latest | `bun_latest` |
| [STA Cloud \| C# / .NET](CGeneric.json) | Dotnet 10 (LTS, Default) | `dotnet_10` |
| [STA Cloud \| C# / .NET](CGeneric.json) | Dotnet 11 (STS) | `dotnet_11` |
| [STA Cloud \| C# / .NET](CGeneric.json) | Dotnet 8 (Legacy, EOL) | `dotnet_8` |
| [STA Cloud \| Go](GolangGeneric.json) | Golang 1.27 (Default) | `golang1.27` |
| [STA Cloud \| Go](GolangGeneric.json) | Golang 1.26 | `golang1.26` |
| [STA Cloud \| Go](GolangGeneric.json) | Golang 1.24 (Legacy) | `golang1.24` |
| [STA Cloud \| Java](JavaGeneric.json) | Java 25 (LTS) | `java_25` |
| [STA Cloud \| Java](JavaGeneric.json) | Java 21 (LTS) | `java_21` |
| [STA Cloud \| Java](JavaGeneric.json) | Java 17 (LTS) | `java_17` |
| [STA Cloud \| Java](JavaGeneric.json) | Java 11 (LTS) | `java_11` |
| [STA Cloud \| Java](JavaGeneric.json) | Java 8 (LTS) | `java_8` |
| [STA Cloud \| Node.js](NodejsGeneric.json) | Nodejs 26 (LTS, Default) | `nodejs_26` |
| [STA Cloud \| Node.js](NodejsGeneric.json) | Nodejs 24 (LTS) | `nodejs_24` |
| [STA Cloud \| Node.js](NodejsGeneric.json) | Nodejs 22 (LTS) | `nodejs_22` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.15 (Stable, Default) | `python_3.15` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.14 (Debian12) | `python_3.14` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.13 (Debian12) | `python_3.13` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.12 (Debian12) | `python_3.12` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.11 (Debian12) | `python_3.11` |
| [STA Cloud \| Python](PythonGeneric.json) | Python 3.10 (Legacy, EOL) (Debian12) | `python_3.10` |
| [STA Cloud \| Rust](RustGeneric.json) | Rust 1.100 (Stable, Default) | `rust_1.100` |
| [STA Cloud \| Rust](RustGeneric.json) | Rust Latest (Rolling stable) | `rust_latest` |

Python 3.15 dùng image stable `python:3.15-slim-bookworm`, thay cho RC trước đây. .NET 10 LTS là mặc định; .NET 11 STS được bổ sung. Java chỉ liệt kê các dòng LTS. Go 1.27 là mặc định mới; 1.26 còn trong danh mục stable upstream. Bun dùng kênh stable `latest`.

Rust mẫu chính thức liệt kê `latest`, `1.60`, `1.56`, `1.31`; đây không phải danh mục các bản Rust mới đầy đủ. Bộ STA Cloud chọn `1.100` và `latest` (rolling stable), không thêm lại ba toolchain lịch sử đó. `rust_1.100` theo nhánh 1.100 và nhận patch mới khi build lại; `rust_latest` dùng upstream `rust:1-bookworm`.

## Biến cấu hình

Chọn phiên bản bằng Docker Image trên Panel, không có biến phiên bản riêng. Tất cả biến dưới đây cho phép người dùng xem và sửa; giá trị rỗng được ghi là `(trống)`.

Ứng dụng HTTP phải lắng nghe `0.0.0.0` và cổng allocation của server (`SERVER_PORT`, do Panel cấp). Egg không tự sửa source hoặc tự truyền cổng cho mọi framework.

### STA Cloud | Bun

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `GIT_ADDRESS` | `(trống)` | Git repo to clone    I.E. https://github.com/STA-Cloud-Dev/repo_name |
| `BRANCH` | `(trống)` | What branch to pull from github.    Default is blank to pull the repo default branch |
| `USER_UPLOAD` | `0` | 1 skips Git installation and initial cloning; use uploaded files. Set 0 to download the repository. AUTO_UPDATE can update an existing Git checkout in either mode. |
| `AUTO_UPDATE` | `0` | Update the Git repository on startup using the current username/token. Git failures stop startup. Public repos do not require credentials. |
| `MAIN_FILE` | `index.js` | The file or script name that starts the App.    E.g. index.ts, src/index.js, or a package.json script name like start |
| `USERNAME` | `(trống)` | Username to auth with git. |
| `ACCESS_TOKEN` | `(trống)` | Personal Access Token used for Git installation and startup updates. Private GitHub repositories require Contents read access. The token is not saved in the remote URL. |

### STA Cloud | C# / .NET

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `GIT_ADDRESS` | `(trống)` | Git repo to clone    I.E. https://github.com/STA-Cloud-Dev/repo_name |
| `BRANCH` | `(trống)` | What branch to pull from github.    Default is blank to pull the repo default branch |
| `USER_UPLOAD` | `0` | 1 skips Git installation and initial cloning; use uploaded files. Set 0 to download the repository. AUTO_UPDATE can update an existing Git checkout in either mode. |
| `AUTO_UPDATE` | `0` | Update the Git repository on startup using the current username/token. Git failures stop startup. Public repos do not require credentials. |
| `USERNAME` | `(trống)` | Username to auth with git. |
| `ACCESS_TOKEN` | `(trống)` | Personal Access Token used for Git installation and startup updates. Private GitHub repositories require Contents read access. The token is not saved in the remote URL. |
| `PROJECT_FILE` | `(trống)` | The main project file if multiple are present. |
| `PROJECT_DIR` | `/home/container` | The location of the .csproj file directory, not the .sln file. |

### STA Cloud | Go

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `GO_PACKAGE` | `(trống)` | Go package to get and build |
| `EXECUTABLE` | `app` | This is the executable from the build. |

### STA Cloud | Java

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `JARFILE` | `server.jar` |  |

### STA Cloud | Node.js

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `GIT_ADDRESS` | `(trống)` | Git repo to clone    I.E. https://github.com/STA-Cloud-Dev/repo_name |
| `BRANCH` | `(trống)` | The branch to install. |
| `USER_UPLOAD` | `0` | 1 skips Git installation and initial cloning; use uploaded files. Set 0 to download the repository. AUTO_UPDATE can update an existing Git checkout in either mode. |
| `AUTO_UPDATE` | `0` | Update the Git repository on startup using the current username/token. Git failures stop startup. Public repos do not require credentials. |
| `NODE_PACKAGES` | `(trống)` | Install additional node packages.    Use spaces to separate. |
| `USERNAME` | `(trống)` | Username to auth with git. |
| `ACCESS_TOKEN` | `(trống)` | Personal Access Token used for Git installation and startup updates. Private GitHub repositories require Contents read access. The token is not saved in the remote URL. |
| `UNNODE_PACKAGES` | `(trống)` | Uninstall node packages.    Use spaces to separate. |
| `MAIN_FILE` | `index.js` | The file that starts the app.  Can be .js and .ts |
| `NODE_ARGS` | `(trống)` | Any extra arguments for nodejs or ts-node |

### STA Cloud | Python

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `CUSTOM_STARTUP` | `(trống)` | Optional command to run instead of the egg default startup. Leave empty to use the default startup command. |
| `GIT_ADDRESS` | `(trống)` | Git repo to clone    I.E. https://github.com/STA-Cloud-Dev/repo_name |
| `BRANCH` | `(trống)` | What branch to pull from github.    Default is blank to pull the repo default branch |
| `USER_UPLOAD` | `0` | 1 skips Git installation and initial cloning; use uploaded files. Set 0 to download the repository. AUTO_UPDATE can update an existing Git checkout in either mode. |
| `AUTO_UPDATE` | `0` | Update the Git repository on startup using the current username/token. Git failures stop startup. Public repos do not require credentials. |
| `PY_FILE` | `main.py` | The file that starts the App. |
| `PY_PACKAGES` | `(trống)` | Install additional python packages.    Use spaces to separate |
| `USERNAME` | `(trống)` | Username to auth with git. |
| `ACCESS_TOKEN` | `(trống)` | Personal Access Token used for Git installation and startup updates. Private GitHub repositories require Contents read access. The token is not saved in the remote URL. |
| `REQUIREMENTS_FILE` | `requirements.txt` | if there are other requirements files to choose from. |

### STA Cloud | Rust

| Biến | Mặc định | Chức năng |
| --- | --- | --- |
| `GIT_ADDRESS` | `(trống)` | Git repo to clone    I.E. https://github.com/STA-Cloud-Dev/repo_name |
| `BRANCH` | `(trống)` | What branch to pull from github.    Default is blank to pull the repo default branch |
| `USER_UPLOAD` | `0` | 1 skips Git installation and initial cloning; use uploaded files. Set 0 to download the repository. AUTO_UPDATE can update an existing Git checkout in either mode. |
| `AUTO_UPDATE` | `0` | Update the Git repository on startup using the current username/token. Git failures stop startup. Public repos do not require credentials. |
| `USERNAME` | `(trống)` | Username to auth with git. |
| `ACCESS_TOKEN` | `(trống)` | Personal Access Token used for Git installation and startup updates. Private GitHub repositories require Contents read access. The token is not saved in the remote URL. |
| `CARGO_MANIFEST` | `Cargo.toml` | Path to Cargo.toml relative to /home/container. |
| `CARGO_PROFILE` | `release` | release builds optimized code; debug builds faster. |
| `CARGO_PACKAGE` | `(trống)` | Optional workspace package name (--package). |
| `CARGO_BIN` | `(trống)` | Optional binary target (--bin); required when the manifest has multiple binaries without default-run. |
| `CARGO_FEATURES` | `(trống)` | Optional features separated by commas or spaces; passed as one --features argument. |
| `CARGO_LOCKED` | `0` | 1 requires an existing up-to-date Cargo.lock; 0 lets Cargo resolve and update it. |
| `APP_ARGS` | `(trống)` | Arguments after cargo run --. Split on whitespace; shell quoting/expansion is not interpreted. |

## Hai cách build

| Ngôn ngữ | GitHub-hosted | Self-hosted |
| --- | --- | --- |
| Node.js | [build nodejs](../../.github/workflows/nodejs.yml) | [build nodejs (self-hosted)](../../.github/workflows/nodejs-selfhosted.yml) |
| Bun | [build bun](../../.github/workflows/bun.yml) | [build bun (self-hosted)](../../.github/workflows/bun-selfhosted.yml) |
| Python | [build python](../../.github/workflows/python.yml) | [build python (self-hosted)](../../.github/workflows/python-selfhosted.yml) |
| C# / .NET | [build c](../../.github/workflows/c.yml) | [build c (self-hosted)](../../.github/workflows/c-selfhosted.yml) |
| Java | [build java](../../.github/workflows/java.yml) | [build java (self-hosted)](../../.github/workflows/java-selfhosted.yml) |
| Go | [build golang](../../.github/workflows/golang.yml) | [build golang (self-hosted)](../../.github/workflows/golang-selfhosted.yml) |
| Rust | [build rust](../../.github/workflows/rust.yml) | [build rust (self-hosted)](../../.github/workflows/rust-selfhosted.yml) |

Tất cả chạy thủ công bằng `workflow_dispatch`, build `linux/amd64` và `linux/arm64`, rồi push cùng tag lên GHCR. Chỉ chạy một trong hai workflow cho cùng phiên bản tại một thời điểm để tránh ghi đè tag đang build. Self-hosted cần runner có nhãn `self-hosted, linux`, Docker và quyền dùng QEMU/binfmt. Mỗi phiên bản là một job; số runner rảnh quyết định số job chạy đồng thời.

Đăng nhập GHCR bằng `USER_TOKEN` nếu đã cấu hình, nếu không dùng `GITHUB_TOKEN` với `packages: write`. Không cần đưa token vào egg. GitHub-hosted dùng cache GHA; self-hosted dùng cache registry/inline.

## Cài đặt và nâng cấp

1. Chạy workflow của ngôn ngữ cần dùng và chờ publish image thành công.
2. Cho Wings pull image mới có `/opt/stacloud/code-languages/start.sh`.
3. Import JSON tương ứng vào Panel. Với server cũ, kiểm tra riêng startup và image đang chọn; thay default trong JSON không tự đổi image của mọi server cũ.
4. Giữ nguyên dữ liệu, Git token, branch và biến của server. Không cần xóa file ứng dụng để đổi thương hiệu.

Rust mặc định chạy `cargo build --release`, rồi `cargo run --release -- ...`. Build lỗi sẽ dừng trước tín hiệu startup. Với nhiều binary, chọn `CARGO_BIN`; workspace có thể chọn `CARGO_PACKAGE`. `CARGO_LOCKED=1` yêu cầu Cargo.lock hợp lệ. `APP_ARGS` tách theo khoảng trắng, không xử lý quote hoặc shell expansion. Cargo cache và target nằm trong dữ liệu server nên có thể tái sử dụng sau restart. Tín hiệu startup thể hiện bước chuẩn bị đã xong, không phải kiểm tra HTTP readiness của ứng dụng.

Go giữ cách cài `GO_PACKAGE` khi install/reinstall hoặc chạy binary upload; đổi `GO_PACKAGE` không tự rebuild ở mỗi restart. Java nhận JAR upload. Các egg Git còn lại clone lúc install và chỉ pull lúc startup khi `AUTO_UPDATE=1`.

## Thư mục runtime dùng chung

`../../code-languages/` là source runtime đang được mọi image sử dụng, không phải thư mục thừa. `start.sh` khởi động từng ngôn ngữ; `git-sync.sh` xử lý Git và token qua askpass; `sync.py` đồng bộ bản sao vào từng build context và nhúng installer vào JSON. Xóa thư mục này sẽ làm mất nguồn đồng bộ.

Sau khi sửa runtime:

```sh
python code-languages/sync.py
python code-languages/sync.py --check
python -m unittest discover -s code-languages -p test_runtime.py -v
```

## Nguồn đối chiếu

- [Pterodactyl Rust Generic](https://eggs.pterodactyl.io/egg/generic-rust-generic/) và [JSON nguồn](https://github.com/pterodactyl/generic-eggs/blob/main/rust/egg-rust-generic.json).
- [Docker Rust official images](https://github.com/docker-library/official-images/blob/master/library/rust).
- [Docker Python official images](https://github.com/docker-library/official-images/blob/master/library/python).
- [.NET release index](https://raw.githubusercontent.com/dotnet/core/main/release-notes/releases-index.json).
- [Node.js release schedule](https://github.com/nodejs/Release/blob/main/schedule.json).
- [Go stable downloads](https://go.dev/dl/?mode=json).

Kiểm tra local không thay thế việc build Docker và chạy ứng dụng thực tế trên Wings.
