# Codyssey_01

## 1. 설치 명령 실행 및 설치 과정 확인
- 가상 머신 플랫폼 활성화 완료 메시지 확인
- 재부팅 전 wsl --status에서 미설치로 표시되는 현상 확인

```text
PS C:\WINDOWS\system32> wsl --status
Linux용 Windows 하위 시스템 설치되어 있지 않습니다. 'wsl.exe --install'을 실행하여 설치할 수 있습니다.
자세한 내용은 https://aka.ms/wslinstall
 참조하세요.

PS C:\Users\User> wsl --install -d Ubuntu
다운로드 중: Linux용 Windows 하위 시스템 3.0.3
설치 중: Linux용 Windows 하위 시스템 3.0.3
Linux용 Windows 하위 시스템 3.0.3이(가) 설치되었습니다.
Windows 선택적 구성 요소 설치 중: VirtualMachinePlatform

배포 이미지 서비스 및 관리 도구
버전: 10.0.26100.9549

이미지 버전: 10.0.26300.9711

기능을 사용하도록 설정하는 중
[==========================100.0%==========================]
작업을 완료했습니다.
요청한 작업이 잘 실행되었습니다. 시스템을 다시 시작하면 변경 사항이 적용됩니다.
요청한 작업이 잘 실행되었습니다. 시스템을 다시 시작하면 변경 사항이 적용됩니다.
```

- WSL 3.0.3 설치 완료 메시지 확인
- VirtualMachinePlatform 기능 활성화 완료
- 시스템 재시작 후 변경 사항 적용 필요 메시지 확인
- 교육장 PC의 초기화 환경으로 인해 재부팅 보류
 
<img width="872" height="627" alt="02_wsl_status" src="https://github.com/user-attachments/assets/d323acbd-4c60-4320-bf93-777c5470add1" />
<img width="731" height="305" alt="02_wsl_status_02" src="https://github.com/user-attachments/assets/af4247e5-ed2b-4ae8-bc76-593cdcf0b369" />


## 2. Docker와 Git 명령어 실행 확인
- Docker: 명령어 인식 불가 (설치 여부 또는 PATH 확인 필요)
- Git: 명령어 인식 불가 (설치 여부 또는 PATH 확인 필요)
- VS Code: 버전 1.144.1 확인

```text
PS C:\Users\User> docker --version
docker : 'docker' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램 이름으로 인식되지
않습니다. 이름이 정확한지 확인하고 경로가 포함된 경우 경로가 올바른지 검증한 다음 다시 시도하십시오.
위치 줄:1 문자:1
+ docker --version
+ ~~~~~~
    + CategoryInfo          : ObjectNotFound: (docker:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\Users\User> git --version
git : 'git' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램 이름으로 인식되지 않습니
다. 이름이 정확한지 확인하고 경로가 포함된 경우 경로가 올바른지 검증한 다음 다시 시도하십시오.
위치 줄:1 문자:1
+ git --version
+ ~~~
    + CategoryInfo          : ObjectNotFound: (git:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\Users\User> code --version
1.144.1
261c84cb1eddf11235f9e2c921425e9663fbe556
x64
```

<img width="876" height="610" alt="03_program_check" src="https://github.com/user-attachments/assets/24195567-6db4-44b5-9995-aa8c5b51bf6f" />


## 3. Get-Location 입력 
- 현재 내가 어느 폴더에 있는지 명령어를 입력하여 확인.

```text
PS C:\Users\User> Get-Location

Path
----
C:\Users\User
```


## 4. Get-ChildItem 입력 
- 현재 있는 폴더 안에 어떤 폴더와 파일들이 있는지 알려주는 명령어를 입력하여 확인.

```text
PS C:\Users\User> Get-ChildItem


    디렉터리: C:\Users\User


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-05   오후 4:11                .copilot
d-----      2026-11-05   오후 4:11                .vscode
d-----      2026-11-05   오후 4:11                .vscode-shared
d-r---      2026-10-14   오후 6:07                Contacts
d-r---      2026-11-06  오후 12:04                Desktop
d-r---      2026-10-14   오후 6:07                Documents
d-r---      2026-10-22   오전 9:33                Downloads
d-r---      2026-10-14   오후 6:07                Favorites
d-----      2026-10-14   오후 6:54                Intel
d-r---      2026-10-14   오후 6:07                Links
d-r---      2026-10-14   오후 6:07                Music
d-r---      2026-10-14   오후 6:08                OneDrive
d-r---      2026-10-14   오후 6:07                Pictures
d-r---      2026-10-14   오후 6:07                Saved Games
d-r---      2026-10-14   오후 6:27                Searches
d-r---      2026-10-15   오전 9:30                Videos
```

<img width="597" height="592" alt="04_terminal_basic" src="https://github.com/user-attachments/assets/0bc3f3af-3937-495b-b823-2e74e1a37ce4" />


## 5. 폴더 이동 및 현재 위치 확인

```text
PS C:\Users\User> cd Desktop
PS C:\Users\User\Desktop> Get-Location

Path
----
C:\Users\User\Desktop
```

<img width="361" height="117" alt="05_folder_navigation" src="https://github.com/user-attachments/assets/34e328d5-01a0-409d-93ac-ba0dbb2d80a3" />


## 6. 파일 생성 및 관리
- PowerShell에서 폴더와 파일을 만들고, 내용을 입력하고, 확인하고, 복사하고, 삭제.

```text
PS C:\Users\User> mkdir Codyssey_Practice


    디렉터리: C:\Users\User


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-07   오후 9:06                Codyssey_Practice


PS C:\Users\User> cd Codyssey_practice
PS C:\Users\User\Codyssey_practice> New-Item test.txt -ItemType File


    디렉터리: C:\Users\User\Codyssey_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-07   오후 9:08              0 test.txt


PS C:\Users\User\Codyssey_practice> Set-Content test.txt "Hello, Codyssey!"
PS C:\Users\User\Codyssey_practice> Get-Content test.txt
Hello, Codyssey!
PS C:\Users\User\Codyssey_practice> Copy-Item test.txt test_copy.txt
PS C:\Users\User\Codyssey_practice> Copy-Item test_copy.txt test_01.txt
PS C:\Users\User\Codyssey_practice> Rename-Item test_copy.txt backup.txt
PS C:\Users\User\Codyssey_practice> Get-ChildItem


    디렉터리: C:\Users\User\Codyssey_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-07   오후 9:10             18 backup.txt
-a----      2026-11-07   오후 9:10             18 test.txt
-a----      2026-11-07   오후 9:10             18 test_01.txt


PS C:\Users\User\Codyssey_practice> Remove_Item backup.txt
Remove_Item : 'Remove_Item' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램 이름으로
인식되지 않습니다. 이름이 정확한지 확인하고 경로가 포함된 경우 경로가 올바른지 검증한 다음 다시 시도
하십시오.
위치 줄:1 문자:1
+ Remove_Item backup.txt
+ ~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (Remove_Item:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\Users\User\Codyssey_practice> Remove-Item backup.txt
PS C:\Users\User\Codyssey_practice> Get-ChildItem


    디렉터리: C:\Users\User\Codyssey_practice


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-07   오후 9:10             18 test.txt
-a----      2026-11-07   오후 9:10             18 test_01.txt
```

-  '-'를 입력해야 하는데 '_'를 입력하여 오류 발생 -> '-'로 다시 입력하여 문제 해결
  
<img width="887" height="317" alt="06_file_management_02" src="https://github.com/user-attachments/assets/efb88d44-dbf9-489f-9f29-0fa5ee0001a2" />
<img width="921" height="967" alt="06_file_management_01" src="https://github.com/user-attachments/assets/5c142096-1a43-4d5c-8ca9-34101e6801fd" />


## 7. 파일 권한 확인 및 변경
- Get-Acl, icacls의 역할과 권한 변경 결과.
- 파일을 누가 읽고, 수정하고, 실행할 수 있는지 정함.
- 현재 사용자에게 수정 권한을 추가했으며, 기존의 상속된 전체 제어 권한은 유지됨.

```text
PS C:\Users\User\Codyssey_practice> Get-Acl test.txt


    디렉터리: C:\Users\User\Codyssey_practice


Path     Owner                  Access
----     -----                  ------
test.txt BUILTIN\Administrators NT AUTHORITY\SYSTEM Allow  FullControl...


PS C:\Users\User\Codyssey_practice> (Get-Acl test.txt).Access


FileSystemRights  : FullControl
AccessControlType : Allow
IdentityReference : NT AUTHORITY\SYSTEM
IsInherited       : True
InheritanceFlags  : None
PropagationFlags  : None

FileSystemRights  : FullControl
AccessControlType : Allow
IdentityReference : BUILTIN\Administrators
IsInherited       : True
InheritanceFlags  : None
PropagationFlags  : None

FileSystemRights  : FullControl
AccessControlType : Allow
IdentityReference : 4F-81\User
IsInherited       : True
InheritanceFlags  : None
PropagationFlags  : None



PS C:\Users\User\Codyssey_practice> icacls test.txt
test.txt NT AUTHORITY\SYSTEM:(I)(F)
         BUILTIN\Administrators:(I)(F)
         4F-81\User:(I)(F)

1 파일을 처리했으며 0 파일은 처리하지 못했습니다.
PS C:\Users\User\Codyssey_practice> icacls test.txt /grant "$($env:USERNAME):(M)"
처리된 파일: test.txt
1 파일을 처리했으며 0 파일은 처리하지 못했습니다.
PS C:\Users\User\Codyssey_practice> icacls test.txt
test.txt 4F-81\User:(M)
         NT AUTHORITY\SYSTEM:(I)(F)
         BUILTIN\Administrators:(I)(F)
         4F-81\User:(I)(F)

1 파일을 처리했으며 0 파일은 처리하지 못했습니다.
```

<img width="762" height="981" alt="07_file_permissions_01" src="https://github.com/user-attachments/assets/cb778f62-3646-4e92-83b2-26824877ad7f" />


## 8. Docker 설치 및 환경 확인
- 교육장 컴퓨터 재시작 시 프로그램이 지워지는 관계로 8번부터는 개인 노트북으로 과제를 진행.

----
- wsl 확인

```text
PS C:\WINDOWS\system32> wsl --version
WSL 버전: 3.0.1.0
커널 버전: 6.18.40.1-1
WSLg 버전: 1.0.79
MSRDC 버전: 1.2.7214
Direct3D 버전: 1.611.1-81528511
DXCore 버전: 10.0.26100.1-240331-1435.ge-release
Windows 버전: 10.0.19045.6466

PS C:\WINDOWS\system32> wsl --list --verbose
  NAME      STATE           VERSION
* Ubuntu    Running         2
```

<img width="803" height="606" alt="08_03_wsl_ready" src="https://github.com/user-attachments/assets/5ae8a740-dbc6-47ad-ae7b-fb7cfabca524" />

----
- docker engine check

```text
PS C:\WINDOWS\system32> docker version
Client:
 Version:           29.9.2
 API version:       1.56
 Go version:        go1.26.10
 Git commit:        a82e528
 Built:             Tue Oct 20 19:44:07 2026
 OS/Arch:           windows/amd64
 Context:           desktop-linux

Server: Docker Desktop 4.98.0 (245422)
 Engine:
  Version:          29.9.2
  API version:      1.56 (minimum version 1.40)
  Go version:       go1.26.10
  Git commit:       0367cbe
  Built:            Tue Oct 20 18:45:02 2026
  OS/Arch:          linux/amd64
  Experimental:     false
 containerd:
  Version:          v2.4.2
  GitCommit:        b7a25261e029d68978bbf290df0a62fc819b3c51
 runc:
  Version:          1.5.2
  GitCommit:        v1.5.2-0-g29dd3dc2
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
PS C:\WINDOWS\system32> docker compose version
Docker Compose version v5.6.1
PS C:\WINDOWS\system32> docker info
Client:
 Version:    29.9.2
 Context:    desktop-linux
 Debug Mode: false
 Plugins:
  agent: Docker AI Agent Runner (Docker Inc.)
    Version:  v1.152.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-agent.exe
  ai: Docker AI Agent - Ask Gordon (Docker Inc.)
    Version:  v1.33.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-ai.exe
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.38.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-buildx.exe
  compose: Docker Compose (Docker Inc.)
    Version:  v5.6.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-compose.exe
  debug: Get a shell into any image or container (Docker Inc.)
    Version:  0.49.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-debug.exe
  desktop: Docker Desktop commands (Docker Inc.)
    Version:  4.98.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-desktop.exe
  dhi: CLI for managing Docker Hardened Images (Docker Inc.)
    Version:  v0.0.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-dhi.exe
  extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.32
    Path:     C:\Program Files\Docker\cli-plugins\docker-extension.exe
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v1.4.1
    Path:     C:\Program Files\Docker\cli-plugins\docker-init.exe
  mcp: Docker MCP Plugin (Docker Inc.)
    Version:  v0.44.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-mcp.exe
  model: Docker Model Runner (Docker Inc.)
    Version:  v1.2.9
    Path:     C:\Program Files\Docker\cli-plugins\docker-model.exe
  offload: Docker Offload (Docker Inc.)
    Version:  v0.7.35
    Path:     C:\Program Files\Docker\cli-plugins\docker-offload.exe
  pass: Docker Pass Secrets Manager Plugin (beta) (Docker Inc.)
    Version:  v0.3.2
    Path:     C:\Program Files\Docker\cli-plugins\docker-pass.exe
  sandbox: "docker sandbox" is deprecated, use Docker Sandboxes instead (Docker Inc.)
    Version:  v0.13.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-sandbox.exe
  scout: Docker Scout (Docker Inc.)
    Version:  v1.27.0
    Path:     C:\Program Files\Docker\cli-plugins\docker-scout.exe

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 29.9.2
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: local
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Discovered Devices:
  cdi: docker.com/gpu=webgpu
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 nvidia runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: b7a25261e029d68978bbf290df0a62fc819b3c51
 runc version: v1.5.2-0-g29dd3dc2
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.18.40.1-microsoft-standard-WSL2
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 8
 Total Memory: 7.705GiB
 Name: docker-desktop
 ID: ce3b289c-d204-4325-8a8c-be6f529c2be9
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Labels:
  com.docker.desktop.address=npipe://\\.\pipe\docker_cli
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  127.0.0.0/8
  ::1/128
 Live Restore Enabled: false
 Firewall Backend: iptables
```

<img width="432" height="424" alt="08_04_docker_engine_check_01" src="https://github.com/user-attachments/assets/0012f950-8042-4acc-88b7-9cf29fe5ac6b" />
<img width="610" height="732" alt="08_04_docker_engine_check_02" src="https://github.com/user-attachments/assets/f256c0ff-e6cb-4bd3-a1bd-d91e7b441fbb" />
<img width="530" height="769" alt="08_04_docker_engine_check_03" src="https://github.com/user-attachments/assets/1d5bb4bd-e4d7-4491-b460-01fc6af3bea4" />


## 9. Docker 컨테이너 실행 및 관리
- Unable to find image ... locally: 로컬에 이미지가 없어 다운로드를 시작한 것이며, 이후 다운로드와 실행이 성공함.
- Hello World의 Exited (0): 메시지를 출력한 후 정상 종료됨.
- Ubuntu에서 exit 실행: 이번 컨테이너의 주 실행 프로세스인 bash가 종료되어 컨테이너도 종료됨.
- docker start -ai: 기존 컨테이너를 다시 시작하고 터미널에 연결함.

----
- Docker 컨테이너 실행

```text
PS C:\WINDOWS\system32> docker run --name codyssey-hello hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
4f55086f7dd0: Pull complete
d5e71e642bf5: Download complete
Digest: sha256:c567b231f65614688711a75f31518a064258a51d442117a3e771a3a8fdba78ef
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```

 <img width="565" height="404" alt="09_01_hello_world" src="https://github.com/user-attachments/assets/185b3a95-6df5-4a80-a69e-849902d7ec06" />
----

- 컨테이너와 이미지 목록 확인

```text
PS C:\WINDOWS\system32> docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
PS C:\WINDOWS\system32> docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED         STATUS                     PORTS     NAMES
9b07db8a5302   hello-world   "/hello"   2 minutes ago   Exited (0) 2 minutes ago             codyssey-hello
PS C:\WINDOWS\system32> docker images
                                                                                                               i Info →   U  In Use
IMAGE                ID             DISK USAGE   CONTENT SIZE   EXTRA
hello-world:latest   c567b231f656       25.9kB         9.49kB    U
```

<img width="929" height="134" alt="09_02_container_list" src="https://github.com/user-attachments/assets/56f21558-e81b-4b78-a762-551ffd6e0398" />
----

- Ubuntu 실행 후 정보 확인

```text
PS C:\WINDOWS\system32> docker run -it --name codyssey-ubuntu ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
f3f25b84a7d7: Pull complete
edafa32f5d9e: Pull complete
21594acc2d8b: Download complete
Digest: sha256:6a06111c3b0a8600feadb270aec771dc239bf407b25625f93f44ab00e11f4d3c
Status: Downloaded newer image for ubuntu:latest
root@bcb80ac5ecac:/# cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
```

<img width="588" height="313" alt="09_03_ubuntu_container" src="https://github.com/user-attachments/assets/42fa7673-ba61-44aa-b5bf-f1c627e88127" />
----

- 컨테이너에서 나가고 재실행

```text
root@bcb80ac5ecac:/# exit
exit
PS C:\WINDOWS\system32> docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
bcb80ac5ecac   ubuntu        "bash"     8 minutes ago    Exited (0) 16 seconds ago             codyssey-ubuntu
9b07db8a5302   hello-world   "/hello"   14 minutes ago   Exited (0) 14 minutes ago             codyssey-hello
PS C:\WINDOWS\system32> docker start -ai codyssey-ubuntu
root@bcb80ac5ecac:/# cat /etc/os-release
PRETTY_NAME="Ubuntu 26.04.1 LTS"
NAME="Ubuntu"
VERSION_ID="26.04"
VERSION="26.04.1 LTS (Resolute Raccoon)"
VERSION_CODENAME=resolute
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=resolute
LOGO=ubuntu-logo
root@bcb80ac5ecac:/# exit
exit
```

<img width="784" height="325" alt="09_04_container_restart" src="https://github.com/user-attachments/assets/388224cf-08b3-4aae-be23-95e6851290c4" />
---

## 10. Dockerfile 작성 및 웹 서버 실행




## 11. 포트 포워딩

## 12. Bind Mount

## 13. Docker Volume 및 데이터 유지

## 14. Git 및 GitHub 연동
````text
PS C:\WINDOWS\system32> git --version
git version 2.56.0.windows.4
PS C:\WINDOWS\system32> code --version
1.143.1
e646868227c3e3a9e3f24277c8c7220be42c0be7
x64
````
<img width="295" height="91" alt="14_01_git_vscode_check" src="https://github.com/user-attachments/assets/3558f951-ed51-492f-beed-08a2662ef974" />


## 15. 트러블슈팅
- VS Code는 설치 성공, Git은 다운로드 중 시간 초과(504 오류)로 실패
- 다시 다운로드를 실행해봤지만 동일하게 504 오류 발생
- 인터넷에 접속 -> Git 공식 Windows 설치 페이지에서 Git for Windows/x64 Setup 파일을 다운받아 직접 설치 -> Git 설치 (문제 해결)
- 오류 발생 화면은 캡처하지 못하여 터미널의 실제 출력 내용을 텍스트로만 첨부
- 공식 설치 파일로 직접 설치한 뒤, git --version으로 정상 실행을 확인하고 해당 내용을 텍스트와 화면 캡처로 첨부
----

- 오류 발생 내용
````text
PS C:\WINDOWS\system32> winget install --id Git.Git -e --source winget
찾음 Git [Git.Git] 버전 2.56.0.4
이 응용 프로그램의 라이선스는 그 소유자가 사용자에게 부여했습니다.
Microsoft는 타사 패키지에 대한 책임을 지지 않고 라이선스를 부여하지도 않습니다.
다운로드 중 https://github.com/git-for-windows/git/releases/download/v2.56.0.windows.4/Git-2.56.0.4-64-bit.exe
명령을 실행하는 동안 예기치 않은 오류가 발생했습니다.
Download request status is not success.
0x801901f8 : Gateway timeout (504).
PS C:\WINDOWS\system32> winget install --id Microsoft.VisualStudioCode -e --source winget
찾음 Microsoft Visual Studio Code [Microsoft.VisualStudioCode] 버전 1.143.1
이 응용 프로그램의 라이선스는 그 소유자가 사용자에게 부여했습니다.
Microsoft는 타사 패키지에 대한 책임을 지지 않고 라이선스를 부여하지도 않습니다.
다운로드 중 https://vscode.download.prss.microsoft.com/dbazure/download/stable/e646868227c3e3a9e3f24277c8c7220be42c0be7/VSCodeUserSetup-x64-1.143.1.exe
  ██████████████████████████████   237 MB /  237 MB
설치 관리자 해시를 확인했습니다.
패키지 설치를 시작하는 중...
설치 성공
````
----

- 오류 해결 후
````text
PS C:\WINDOWS\system32> git --version
git version 2.56.0.windows.4
PS C:\WINDOWS\system32> code --version
1.143.1
e646868227c3e3a9e3f24277c8c7220be42c0be7
x64
````
<img width="295" height="91" alt="14_01_git_vscode_check" src="https://github.com/user-attachments/assets/3558f951-ed51-492f-beed-08a2662ef974" />

## 16. 최종 결과





