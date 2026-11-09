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
```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> wsl -d Ubuntu
kjh@admin:/mnt/c/Users/KJH/source/Codyssey_01/WebServer$ cd ~
kjh@admin:~$ mkdir -p codyssey-week01/permissions
kjh@admin:~$ cd codyssey-week01
kjh@admin:~/codyssey-week01$ pwd
/home/kjh/codyssey-week01
kjh@admin:~/codyssey-week01$ touch empty.txt .hidden-note
kjh@admin:~/codyssey-week01$ echo "Hello, Linux CLI!" > note.txt
kjh@admin:~/codyssey-week01$ ls -la
total 16
drwxr-xr-x 3 kjh kjh 4096 Nov  8 20:01 .
drwxr-x--- 5 kjh kjh 4096 Nov  8 19:59 ..
-rw-r--r-- 1 kjh kjh    0 Nov  8 20:00 .hidden-note
-rw-r--r-- 1 kjh kjh    0 Nov  8 20:00 empty.txt
-rw-r--r-- 1 kjh kjh   18 Nov  8 20:01 note.txt
drwxr-xr-x 2 kjh kjh 4096 Nov  8 19:59 permissions
kjh@admin:~/codyssey-week01$ cat note.txt
Hello, Linux CLI!
kjh@admin:~/codyssey-week01$ cp not.txt note_copy.txt      안)
cp: cannot stat 'not.txt': No such file or directory
kjh@admin:~/codyssey-week01$ cp note.txt note_copy.txt
kjh@admin:~/codyssey-week01$ mv note_copy.txt renamed.txt
kjh@admin:~/codyssey-week01$ mv renamed.txt permissions/
kjh@admin:~/codyssey-week01$ ls -la permissions/renamed.txt
-rw-r--r-- 1 kjh kjh 18 Nov  8 20:02 permissions/renamed.txt
kjh@admin:~/codyssey-week01$ cp note.txt note_copy.txt
kjh@admin:~/codyssey-week01$ mv note_copy.txt renamed.txt
kjh@admin:~/codyssey-week01$ mv renamed.txt permissions/
kjh@admin:~/codyssey-week01$ ls -la permissions
total 12
drwxr-xr-x 2 kjh kjh 4096 Nov  8 20:04 .
drwxr-xr-x 3 kjh kjh 4096 Nov  8 20:04 ..
-rw-r--r-- 1 kjh kjh   18 Nov  8 20:04 renamed.txt
kjh@admin:~/codyssey-week01$ rm permissions/renamed.txt
kjh@admin:~/codyssey-week01$ ls -la permissionscp note.txt note_copy.txt
ls: cannot access 'permissionscp': No such file or directory
ls: cannot access 'note_copy.txt': No such file or directory
-rw-r--r-- 1 kjh kjh 18 Nov  8 20:01 note.txt
kjh@admin:~/codyssey-week01$ mv note_copy.txt renamed.txt
mv: cannot stat 'note_copy.txt': No such file or directory
kjh@admin:~/codyssey-week01$ mv renamed.txt permissions/
mv: cannot stat 'renamed.txt': No such file or directory
kjh@admin:~/codyssey-week01$ ls -la permissions
total 8                                                      .
drwxr-xr-x 2 kjh kjh 4096 Nov  8 20:04 .
drwxr-xr-x 3 kjh kjh 4096 Nov  8 20:04 ..
```

-  '-'를 입력해야 하는데 '_'를 입력하여 오류 발생 -> '-'로 다시 입력하여 문제 해결
  
<img width="887" height="317" alt="06_file_management_02" src="https://github.com/user-attachments/assets/efb88d44-dbf9-489f-9f29-0fa5ee0001a2" />
<img width="921" height="967" alt="06_file_management_01" src="https://github.com/user-attachments/assets/5c142096-1a43-4d5c-8ca9-34101e6801fd" />
<img width="540" height="915" alt="6_7_" src="https://github.com/user-attachments/assets/d0109caf-bdf9-4946-b00c-b5c24f1ec1d2" />


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
```text
kjh@admin:~/codyssey-week01$ stat -c '%a %A %n' note.txt permissions
644 -rw-r--r-- note.txt                                              .
755 drwxr-xr-x permissions
kjh@admin:~/codyssey-week01$ chmod 600 note.txt
kjh@admin:~/codyssey-week01$ chmod 700 permissions
kjh@admin:~/codyssey-week01$ stat -c '%a %A %n' note.txt permissions
600 -rw------- note.txt
700 drwx------ permissions
kjh@admin:~/codyssey-week01$ chmod 644 note.txt
kjh@admin:~/codyssey-week01$ chmod 755 permissions
kjh@admin:~/codyssey-week01$ stat -c '%a %A %n' note.txt permissions
644 -rw-r--r-- note.txt
755 drwxr-xr-x permissions
```

<img width="762" height="981" alt="07_file_permissions_01" src="https://github.com/user-attachments/assets/cb778f62-3646-4e92-83b2-26824877ad7f" />
<img width="540" height="915" alt="6_7_" src="https://github.com/user-attachments/assets/be210049-e096-4595-a9f6-e064c39a1fc7" />


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

- 실행 중인 컨테이너의 CPU·메모리 사용량 등을 한 번 출력하고 종료

```text
PS C:\WINDOWS\system32> docker --version
>> docker ps
>> docker stats --no-stream
Docker version 29.9.2, build a82e528
CONTAINER ID   IMAGE          COMMAND                   CREATED          STATUS          PORTS                    NAMES
466be0abdd8b   nginx:alpine   "/docker-entrypoint.…"   45 minutes ago   Up 45 minutes   127.0.0.1:8080->80/tcp   codyssey-server
CONTAINER ID   NAME              CPU %     MEM USAGE / LIMIT     MEM %     NET I/O          BLOCK I/O     PIDS
466be0abdd8b   codyssey-server   0.00%     7.266MiB / 7.705GiB   0.09%     5.2kB / 2.67kB   0B / 12.3kB   9
```

<img width="925" height="114" alt="09" src="https://github.com/user-attachments/assets/b87a7b56-0db0-48c4-b57e-fc35e30a9740" />
---

- 주 프로세스를 계속 실행하는 Ubuntu 컨테이너
- 새 컨테이너 생성은 실패했지만, 이어서 입력한 docker exec는 이미 실행 중이던 879189c2ec6e 컨테이너에 연결. 기존 컨테이너에 접속해 실습

```text
PS C:\WINDOWS\system32> docker run -d --name codyssey-exec-demo ubuntu sleep infinity
>> docker exec -it codyssey-exec-demo bash
docker: Error response from daemon: Conflict. The container name "/codyssey-exec-demo" is already in use by container "879189c2ec6ee06cb5ac2a0e04ea2256b9daa8d9cf075c22ae2dfa10ac35c7e6". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information

What's next:
    Debug this container error with Gordon → docker ai "help me fix this container error"
root@879189c2ec6e:/# echo "This shell was started by docker exec"
This shell was started by docker exec
root@879189c2ec6e:/# ls
bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@879189c2ec6e:/# exit
exit

What's next:
    Try Docker Debug for seamless, persistent debugging tools in any container or image → docker debug codyssey-exec-demo
    Learn more at https://docs.docker.com/go/debug-cli/
PS C:\WINDOWS\system32> docker ps --filter name=codyssey-exec-demo
CONTAINER ID   IMAGE     COMMAND            CREATED              STATUS              PORTS     NAMES
879189c2ec6e   ubuntu    "sleep infinity"   About a minute ago   Up About a minute             codyssey-exec-demo
PS C:\WINDOWS\system32> docker stop codyssey-exec-demo
>> docker ps -a --filter name=codyssey-exec-demo
codyssey-exec-demo
CONTAINER ID   IMAGE     COMMAND            CREATED         STATUS                                PORTS     NAMES
879189c2ec6e   ubuntu    "sleep infinity"   2 minutes ago   Exited (137) Less than a second ago             codyssey-exec-demo
PS C:\WINDOWS\system32> docker inspect codyssey-exec-demo --format 'ExitCode={{.State.ExitCode}} OOMKilled={{.State.OOMKilled}}'
ExitCode=137 OOMKilled=false
```
<img width="944" height="386" alt="6_7_2" src="https://github.com/user-attachments/assets/c0d3829b-a3bf-4dd4-803f-f8a2f14d37ae" />


## 10. Dockerfile 작성 및 웹 서버 실행

- Get-Content로 확인한 HTML과 Dockerfile

```text
새로운 크로스 플랫Set-Location "$env:USERPROFILE\source\Codyssey_01"
>> Get-Location
>> git statusJH>

On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
Path
----
C:\Users\KJH\source\Codyssey_01


PS C:\Users\KJH\source\Codyssey_01> git pull --ff-only
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (6/6), 2.54 KiB | 35.00 KiB/s, done.
From https://github.com/KMJ-lroise/Codyssey_01
   da8f8e6..0aa9c85  main       -> origin/main
Updating da8f8e6..0aa9c85
Fast-forward
 README.md | 50 ++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 50 insertions(+)
PS C:\Users\KJH\source\Codyssey_01> New-Item -ItemType Directory -Path .\WebServer\app -Force
>> Set-Location .\WebServer
>> Get-Location


    디렉터리: C:\Users\KJH\source\Codyssey_01\WebServer


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-08   오후 6:59                app

Drive        : C
Provider     : Microsoft.PowerShell.Core\FileSystem
ProviderPath : C:\Users\KJH\source\Codyssey_01\WebServer
Path         : C:\Users\KJH\source\Codyssey_01\WebServer



PS C:\Users\KJH\source\Codyssey_01\WebServer> Set-Content -Path .\app\index.html -Value "<h1>Hello, Codyssey!</h1>" -Encoding utf8
PS C:\Users\KJH\source\Codyssey_01\WebServer> @'
>> FROM nginx:alpine
>> COPY app/index.html /usr/share/nginx/html/index.html
>> EXPOSE 80
>> '@ | Set-Content -Path .\Dockerfile -Encoding ascii
PS C:\Users\KJH\source\Codyssey_01\WebServer> Get-Content .\Dockerfile
>> Get-ChildItem
FROM nginx:alpine
COPY app/index.html /usr/share/nginx/html/index.html
EXPOSE 80


    디렉터리: C:\Users\KJH\source\Codyssey_01\WebServer


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-08   오후 7:00                app
-a----      2026-11-08   오후 7:04             82 Dockerfile
```

<img width="922" height="912" alt="10_01_dockerfile" src="https://github.com/user-attachments/assets/8215fd4d-44de-49d0-865e-8c935aef6d12" />

<img width="1319" height="690" alt="10_index_html" src="https://github.com/user-attachments/assets/c27252b0-e914-4f2d-8b3b-8cdc6b5258bd" />

----

- 빌드 완료 결과와 docker images

```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker build -t codyssey-web .
[+] Building 13.7s (8/8) FINISHED                                                                                docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                             0.2s
 => => transferring dockerfile: 119B                                                                                             0.0s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                                  2.6s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                                     0.0s
 => [internal] load .dockerignore                                                                                                0.1s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load build context                                                                                                0.2s
 => => transferring context: 98B                                                                                                 0.0s
 => [1/2] FROM docker.io/library/nginx:alpine@sha256:713fc2ebfd92e8217db451477182ee91944b123d2b1ee9fd5a8c6e91ca6c3a11            7.0s
 => => resolve docker.io/library/nginx:alpine@sha256:713fc2ebfd92e8217db451477182ee91944b123d2b1ee9fd5a8c6e91ca6c3a11            0.1s
 => => sha256:da90db506dd5f2d604467c4dc38442534f74c9e76c1982df0c262e144bad7bc9 20.55MB / 20.55MB                                 4.7s
 => => sha256:69d81d5522572d5b7abcc8f594ecbc4cf9bea72402675a419e8d7b516e4c3f14 1.40kB / 1.40kB                                   0.5s
 => => sha256:b9c6ee6a30f8811636d7273be348906cf0e4e9725378dd54b7d4a3725538cad4 1.21kB / 1.21kB                                   0.6s
 => => sha256:a746bd1dc828f61bf43b775dcfecb9ded8a3d3b41789915fe135fa6b9fa85965 404B / 404B                                       0.6s
 => => sha256:c7dfd64eeb02740cc41e9f32ad7f75781882d4c167b77427aa9615d1419c4515 629B / 629B                                       0.3s
 => => sha256:e011f124249bf1c4be27b3311c3b40cb90dd7737381af1c62b508020790b7bd5 965B / 965B                                       0.3s
 => => sha256:1abafee971b93c1ae05f03c35c6fb6e3376e75e6f16b590092a822b61ebf10b6 1.94MB / 1.94MB                                   0.9s
 => => sha256:881fc932939efef04ca120ad44bbd2c0917851eb247aa4995428afb1e80ede17 3.85MB / 3.85MB                                   2.1s
 => => extracting sha256:881fc932939efef04ca120ad44bbd2c0917851eb247aa4995428afb1e80ede17                                        0.5s
 => => extracting sha256:1abafee971b93c1ae05f03c35c6fb6e3376e75e6f16b590092a822b61ebf10b6                                        0.6s
 => => extracting sha256:c7dfd64eeb02740cc41e9f32ad7f75781882d4c167b77427aa9615d1419c4515                                        0.1s
 => => extracting sha256:e011f124249bf1c4be27b3311c3b40cb90dd7737381af1c62b508020790b7bd5                                        0.1s
 => => extracting sha256:a746bd1dc828f61bf43b775dcfecb9ded8a3d3b41789915fe135fa6b9fa85965                                        0.1s
 => => extracting sha256:b9c6ee6a30f8811636d7273be348906cf0e4e9725378dd54b7d4a3725538cad4                                        0.1s
 => => extracting sha256:69d81d5522572d5b7abcc8f594ecbc4cf9bea72402675a419e8d7b516e4c3f14                                        0.1s
 => => extracting sha256:da90db506dd5f2d604467c4dc38442534f74c9e76c1982df0c262e144bad7bc9                                        1.2s
 => [2/2] COPY app/index.html /usr/share/nginx/html/index.html                                                                   0.3s
 => exporting to image                                                                                                           2.9s
 => => exporting layers                                                                                                          0.4s
 => => exporting manifest sha256:3b7ad2c835f1482d55d6af0cacaf577066346f28313f7a2872933449e9f5601a                                0.1s
 => => exporting config sha256:d57c6e11ba20f0fc638b1d7c43e242e477b3eb8b39ad2e4c9c8ac6540ee0a6d2                                  0.1s
 => => exporting attestation manifest sha256:ddc1806a2988976189ca46ff2e544eab8a9b42a62266027a7a890327bbaba2cb                    0.2s
 => => exporting manifest list sha256:1f8a2cc0f3601f79196685c0a5542a65481d18b3f563e75d52c944dd1a80e824                           0.1s
 => => naming to docker.io/library/codyssey-web:latest                                                                           0.0s
 => => unpacking to docker.io/library/codyssey-web:latest                                                                        2.0s
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker images
                                                                                                                 i Info →   U  In Use
IMAGE                 ID             DISK USAGE   CONTENT SIZE   EXTRA
codyssey-web:latest   1f8a2cc0f360       93.7MB         26.4MB
hello-world:latest    c567b231f656       25.9kB         9.49kB    U
ubuntu:latest         6a06111c3b0a        163MB         45.9MB    U
```
<img width="945" height="609" alt="10_02_image_build" src="https://github.com/user-attachments/assets/e955e920-41c2-4aa7-b6ec-f3287e2d1ecd" />

----

- docker ps, 로그, 컨테이너 내부 HTML 확인 결과

```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker run -d --name codyssey-server codyssey-web
a3f1ddcec96246e2bdb031377a1bfb9527bad3b47f5ed9560c54be7edc0fbf14
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker ps
CONTAINER ID   IMAGE          COMMAND                   CREATED          STATUS          PORTS     NAMES
a3f1ddcec962   codyssey-web   "/docker-entrypoint.…"   16 seconds ago   Up 15 seconds   80/tcp    codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker logs codyssey-server
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/11/08 10:13:00 [notice] 1#1: using the "epoll" event method
2026/11/08 10:13:00 [notice] 1#1: nginx/1.31.8
2026/11/08 10:13:00 [notice] 1#1: built by gcc 15.2.0 (Alpine 15.2.0)
2026/11/08 10:13:00 [notice] 1#1: OS: Linux 6.18.40.1-microsoft-standard-WSL2
2026/11/08 10:13:00 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2026/11/08 10:13:00 [notice] 1#1: start worker processes
2026/11/08 10:13:00 [notice] 1#1: start worker process 30
2026/11/08 10:13:00 [notice] 1#1: start worker process 31
2026/11/08 10:13:00 [notice] 1#1: start worker process 32
2026/11/08 10:13:00 [notice] 1#1: start worker process 33
2026/11/08 10:13:00 [notice] 1#1: start worker process 34
2026/11/08 10:13:00 [notice] 1#1: start worker process 35
2026/11/08 10:13:00 [notice] 1#1: start worker process 36
2026/11/08 10:13:00 [notice] 1#1: start worker process 37
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker exec codyssey-server cat /usr/share/nginx/html/index.html
﻿<h1>Hello, Codyssey!</h1>
```

<img width="808" height="439" alt="10_03_webserver_running" src="https://github.com/user-attachments/assets/73a6a13c-ffcf-4582-9db8-88e0ca499a43" />


## 11. 포트 포워딩

- 포트를 지정한 실행 명령, docker ps, docker port 결과

```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker stop codyssey-server
codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker rm codyssey-server
codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker run -d --name codyssey-server -p 127.0.0.1:8080:80 codyssey-web
ff3e9215bfe58f62d2b217e69cba6b80ae1f0dd30e1515171ef82b0881a1e6df
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker ps
CONTAINER ID   IMAGE          COMMAND                   CREATED          STATUS          PORTS                    NAMES
ff3e9215bfe5   codyssey-web   "/docker-entrypoint.…"   58 seconds ago   Up 57 seconds   127.0.0.1:8080->80/tcp   codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker port codyssey-server
80/tcp -> 127.0.0.1:8080
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker logs --tail 20 codyssey-server
2026/11/08 10:21:23 [notice] 1#1: using the "epoll" event method
2026/11/08 10:21:23 [notice] 1#1: nginx/1.31.8
2026/11/08 10:21:23 [notice] 1#1: built by gcc 15.2.0 (Alpine 15.2.0)
2026/11/08 10:21:23 [notice] 1#1: OS: Linux 6.18.40.1-microsoft-standard-WSL2
2026/11/08 10:21:23 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2026/11/08 10:21:23 [notice] 1#1: start worker processes
2026/11/08 10:21:23 [notice] 1#1: start worker process 30
2026/11/08 10:21:23 [notice] 1#1: start worker process 31
2026/11/08 10:21:23 [notice] 1#1: start worker process 32
2026/11/08 10:21:23 [notice] 1#1: start worker process 33
2026/11/08 10:21:23 [notice] 1#1: start worker process 34
2026/11/08 10:21:23 [notice] 1#1: start worker process 35
2026/11/08 10:21:23 [notice] 1#1: start worker process 36
2026/11/08 10:21:23 [notice] 1#1: start worker process 37
172.17.0.1 - - [08/Nov/2026:10:25:41 +0000] "GET / HTTP/1.1" 200 30 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/157.0.0.0 Safari/537.36" "-"
172.17.0.1 - - [08/Nov/2026:10:25:41 +0000] "GET /favicon.ico HTTP/1.1" 404 555 "http://localhost:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/157.0.0.0 Safari/537.36" "-"
2026/11/08 10:25:41 [error] 30#30: *1 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
172.17.0.1 - - [08/Nov/2026:10:26:26 +0000] "GET / HTTP/1.1" 200 30 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/157.0.0.0 Safari/537.36 Edg/157.0.0.0" "-"
2026/11/08 10:26:26 [error] 31#31: *3 open() "/usr/share/nginx/html/favicon.ico" failed (2: No such file or directory), client: 172.17.0.1, server: localhost, request: "GET /favicon.ico HTTP/1.1", host: "localhost:8080", referrer: "http://localhost:8080/"
172.17.0.1 - - [08/Nov/2026:10:26:26 +0000] "GET /favicon.ico HTTP/1.1" 404 555 "http://localhost:8080/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/157.0.0.0 Safari/537.36 Edg/157.0.0.0" "-"
```

<img width="921" height="155" alt="11_01_port_mapping" src="https://github.com/user-attachments/assets/0ec1e4bf-22c1-4544-8dd9-499a51830452" />
<img width="943" height="380" alt="11_03_access_log" src="https://github.com/user-attachments/assets/5a6b67c2-ca33-4dc0-beb6-406156b51b75" />
<img width="528" height="359" alt="11_02_browser" src="https://github.com/user-attachments/assets/5235f39f-553e-455d-ac58-b2ab479e64de" />


## 12. Bind Mount

- 파일 수정이 웹페이지에 바로 반영되는지 확인

```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> Set-Location "$env:USERPROFILE\source\Codyssey_01\WebServer"
>> docker stop codyssey-server
>> docker rm codyssey-server
codyssey-server
codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> $appPath = (Resolve-Path .\app).Path
>> docker run -d --name codyssey-server -p 127.0.0.1:8080:80 --mount "type=bind,source=$appPath,target=/usr/share/nginx/html,readonly" nginx:alpine
>> docker ps
Unable to find image 'nginx:alpine' locally
alpine: Pulling from library/nginx
Digest: sha256:713fc2ebfd92e8217db451477182ee91944b123d2b1ee9fd5a8c6e91ca6c3a11
Status: Downloaded newer image for nginx:alpine
466be0abdd8ba536850e2b5b18fba0d2efc385450c3dae3ad058d65fdd8e001f
CONTAINER ID   IMAGE          COMMAND                   CREATED        STATUS                  PORTS                    NAMES
466be0abdd8b   nginx:alpine   "/docker-entrypoint.…"   1 second ago   Up Less than a second   127.0.0.1:8080->80/tcp   codyssey-server
PS C:\Users\KJH\source\Codyssey_01\WebServer> Set-Content -Path .\app\index.html -Value "<h1>Bind Mount Success!</h1>" -Encoding utf8
>> Get-Content .\app\index.html
>> docker exec codyssey-server cat /usr/share/nginx/html/index.html
<h1>Bind Mount Success!</h1>
﻿<h1>Bind Mount Success!</h1>
```
<img width="943" height="310" alt="12_Bind_Mount" src="https://github.com/user-attachments/assets/b2f99431-87d3-4664-b280-2d0f3d12306c" />
- 변경 전
<img width="528" height="359" alt="11_02_browser" src="https://github.com/user-attachments/assets/37c99184-3a79-4f18-81a7-93cf5b511b33" />
- 변경 후
<img width="459" height="222" alt="12_Bind_Mount_Success" src="https://github.com/user-attachments/assets/cd10a750-d9e1-459c-9953-da47f17d3cf5" />

----
- 변경 전: Hello, Codyssey!, 변경 후: Bind Mount Success!
- 파일 수정 후 이미지 재빌드·컨테이너 재시작 없이 반영됐음


## 13. Docker Volume 및 데이터 유지

- 컨테이너를 삭제해도 데이터가 남는지 확인

```text
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker volume create codyssey-data
>> docker volume ls
>> docker run -it --name codyssey-volume-test -v codyssey-data:/data ubuntu bash
codyssey-data                                                                                                          .
DRIVER    VOLUME NAME
local     codyssey-data
root@690d2c1614cb:/# echo "My Docker Volume Data" > /data/test.txt
root@690d2c1614cb:/# cat /data/test.txt
My Docker Volume Data
root@690d2c1614cb:/# exit
exit
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker rm codyssey-volume-test
>> docker volume ls
codyssey-volume-test
DRIVER    VOLUME NAME
local     codyssey-data
PS C:\Users\KJH\source\Codyssey_01\WebServer> docker run -it --name codyssey-volume-check -v codyssey-data:/data ubuntu bash
root@8f9f357e9d6c:/# cat /data/test.txt
My Docker Volume Data
root@8f9f357e9d6c:/# exit
exit
```
<img width="891" height="299" alt="13_Docker Volume" src="https://github.com/user-attachments/assets/72a07d89-21fc-45de-871a-d7e31c01d716" />


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

----

```text
새로운 크로스 플랫폼 PowerShell 사용 https://aka.ms/pscore6
                 New-Item -ItemType Directory -Path "$env:USERPROFILE\source" -Force
>> Set-Location "$env:USERPROFILE\source"


    디렉터리: C:\Users\KJH


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-08   오후 6:25                source


PS C:\Users\KJH\source> git clone https://github.com/KMJ-lroise/Codyssey_01.git
Cloning into 'Codyssey_01'...
remote: Enumerating objects: 45, done.
remote: Counting objects: 100% (45/45), done.
remote: Compressing objects: 100% (29/29), done.
remote: Total 45 (delta 13), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (45/45), 20.84 KiB | 2.08 MiB/s, done.
Resolving deltas: 100% (13/13), done.
PS C:\Users\KJH\source> Set-Location "$env:USERPROFILE\source\Codyssey_01"
>> git status
>> git remote -v
>> Get-ChildItem
>> code .
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
origin  https://github.com/KMJ-lroise/Codyssey_01.git (fetch)
origin  https://github.com/KMJ-lroise/Codyssey_01.git (push)


    디렉터리: C:\Users\KJH\source\Codyssey_01


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-11-08   오후 6:25          23988 README.md
```
<img width="598" height="578" alt="14_02_repository_clone" src="https://github.com/user-attachments/assets/32d82c6f-4a29-4bcf-a19e-e9fedc0bd770" />
----

- vs code 연동
<img width="1436" height="898" alt="VS Code" src="https://github.com/user-attachments/assets/465bdf84-4e87-49d1-9e0a-edb22461f5d8" />

----

### Git 사용자 정보 및 기본 브랜치 설정

- Git 사용자 이름과 GitHub noreply 이메일을 설정했다.
- 기본 브랜치를 main으로 설정했다.
- git config --list 출력으로 설정 내용을 확인했다.

```text
PS C:\Users\KJH\source\Codyssey_01> git config --global user.email "352281822+KMJ-lroise@users.noreply.github.com"
PS C:\Users\KJH\source\Codyssey_01> git config --global user.name "KMJ"
PS C:\Users\KJH\source\Codyssey_01> git config --global init.defaultBranch main
PS C:\Users\KJH\source\Codyssey_01> git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=schannel
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.email=352281822+KMJ-lroise@users.noreply.github.com
user.name=KMJ
init.defaultbranch=main
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
remote.origin.url=https://github.com/KMJ-lroise/Codyssey_01.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
branch.main.vscode-merge-base=origin/main
```

```text
PS C:\Users\KJH\source\Codyssey_01> git config --get init.defaultBranch
main
```

### Dockerfile 및 웹 소스 업로드

- WebServer/Dockerfile과 WebServer/app/index.html을 Git에 추가했다.
- 변경 내용을 확인한 뒤 커밋했다.
- 브라우저 인증 후 GitHub의 main 브랜치로 push했다.
- git status에서 원격 브랜치와 동기화되었으며 작업 폴더에 미커밋 변경이 없음을 확인했다.
- Git push 시 GitHub 로그인 창이 표시되어 브라우저 인증을 진행했다.
- 인증 및 업로드 성공은 아래의 push 성공 로그와 GitHub 저장소 화면으로 확인했다.
- VS Code의 GitHub 로그인 증거는 별도로 기록한다.

```text
PS C:\Users\KJH\source\Codyssey_01> git config --get init.defaultBranch
main
PS C:\Users\KJH\source\Codyssey_01> git add WebServer/Dockerfile WebServer/app/index.html
warning: in the working copy of 'WebServer/Dockerfile', LF will be replaced by CRLF the next time Git touches it
PS C:\Users\KJH\source\Codyssey_01> git diff --cached --stat
 WebServer/Dockerfile     | 3 +++
 WebServer/app/index.html | 1 +
 2 files changed, 4 insertions(+)
PS C:\Users\KJH\source\Codyssey_01> git diff --cached
diff --git a/WebServer/Dockerfile b/WebServer/Dockerfile
new file mode 100644
index 0000000..29887f1
--- /dev/null
+++ b/WebServer/Dockerfile
@@ -0,0 +1,3 @@
+FROM nginx:alpine
+COPY app/index.html /usr/share/nginx/html/index.html
+EXPOSE 80
diff --git a/WebServer/app/index.html b/WebServer/app/index.html
new file mode 100644
index 0000000..f054482
--- /dev/null
+++ b/WebServer/app/index.html
@@ -0,0 +1 @@
+﻿<h1>Bind Mount Success!</h1>
PS C:\Users\KJH\source\Codyssey_01> git commit -m "Add Dockerfile and web page"
[main 3234d6b] Add Dockerfile and web page
 2 files changed, 4 insertions(+)
 create mode 100644 WebServer/Dockerfile
 create mode 100644 WebServer/app/index.html
PS C:\Users\KJH\source\Codyssey_01> git push origin main
info: please complete authentication in your browser...
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 543 bytes | 181.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/KMJ-lroise/Codyssey_01.git
   017ee7a..3234d6b  main -> main
PS C:\Users\KJH\source\Codyssey_01> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

<img width="527" height="449" alt="login" src="https://github.com/user-attachments/assets/ffcb3690-e331-408c-a9db-11c2dc72dd75" />

<img width="926" height="482" alt="git push" src="https://github.com/user-attachments/assets/a3be31d4-1441-492a-bfa8-cfa35b9e800b" />

### VS Code GitHub 로그인 및 저장소 연동 확인

- VS Code 계정 메뉴에서 KMJ-lroise (GitHub) 로그인 상태를 확인했다.
- Codyssey_01 저장소를 열고 WebServer 폴더와 Dockerfile을 확인했다.
- 왼쪽 아래 상태 표시줄에서 현재 브랜치가 main임을 확인했다.
- 아래 화면에는 비밀번호, 토큰, 인증 코드가 포함되어 있지 않다.

<img width="1795" height="1024" alt="VS Code GitHub 로그인 및 저장소 연동" src="https://github.com/user-attachments/assets/0aa06716-7a23-4423-9f7f-917a456373ef" />


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

----
- 6번 파일 생성 및 항목에서 '-'를 입력해야 하는데 '_'를 입력하여 오류 발생 -> '-'로 다시 입력하여 문제 해결
- 6번에서 cp not.txt note_copy.txt	실제 파일명 note.txt를 not.txt로 입력	올바른 이름으로 다시 복사해 성공
- 6번에서 ls -la permissionscp note.txt note_copy.txt	명령 두 개가 줄바꿈 없이 붙음->	ls -la permissions를 다시 실행해 확인
- 이후 mv의 cannot stat	이동하려는 원본 파일이 당시 존재하지 않음 ->	마지막 목록에서 삭제 대상이 없는 상태 확인


## 16. 선택 미션

### Compose 단일 서비스
```text
PS C:\Users\KJH\source\Codyssey_01> New-Item -ItemType Directory -Path .\WebServer\templates -Force
>>
>> @'
>> server {
>>     listen ${NGINX_PORT};
>>     server_name localhost;
>>
>>     location / {
>>         root /usr/share/nginx/html;
>>         index index.html;
>>     }
>> }
>> '@ | Set-Content .\WebServer\templates\default.conf.template -Encoding ascii


    디렉터리: C:\Users\KJH\source\Codyssey_01\WebServer


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-11-09   오후 5:05                templates


PS C:\Users\KJH\source\Codyssey_01> @'
>> services:
>>   web:
>>     build: ./WebServer
>>     ports:
>>       - "127.0.0.1:8081:${NGINX_PORT:-8085}"
>>     environment:
>>       NGINX_PORT: "${NGINX_PORT:-8085}"
>>     volumes:
>>       - ./WebServer/templates/default.conf.template:/etc/nginx/templates/default.conf.template:ro
>> '@ | Set-Content .\docker-compose.yml -Encoding ascii
PS C:\Users\KJH\source\Codyssey_01> docker compose config
>> docker compose up -d --build web
>> docker compose ps
>> curl.exe -i http://localhost:8081
>> docker compose logs --tail 30 web
name: codyssey_01
services:
  web:
    environment:
      NGINX_PORT: "8085"
    networks:
      default: null
    volumes:
      - type: bind
        source: C:\Users\KJH\source\Codyssey_01\WebServer\templates\default.conf.template
        target: /etc/nginx/templates/default.conf.template
        read_only: true
        bind: {}
    build:
      context: C:\Users\KJH\source\Codyssey_01\WebServer
      dockerfile: Dockerfile
    ports:
      - mode: ingress
        host_ip: 127.0.0.1
        target: 8085
        published: "8081"
        protocol: tcp
networks:
  default:
    name: codyssey_01_default
[+] Building 2.5s (9/9) FINISHED
 => [internal] load local bake definitions                                                                                            0.2s
 => => reading from stdin 541B                                                                                                        0.2s
 => [internal] load build definition from Dockerfile                                                                                  0.1s
 => => transferring dockerfile: 119B                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                                       0.1s
 => [internal] load .dockerignore                                                                                                     0.1s
 => => transferring context: 2B                                                                                                       0.0s
 => [internal] load build context                                                                                                     0.1s
 => => transferring context: 101B                                                                                                     0.0s
 => CACHED [1/2] FROM docker.io/library/nginx:alpine@sha256:713fc2ebfd92e8217db451477182ee91944b123d2b1ee9fd5a8c6e91ca6c3a11          0.1s
 => => resolve docker.io/library/nginx:alpine@sha256:713fc2ebfd92e8217db451477182ee91944b123d2b1ee9fd5a8c6e91ca6c3a11                 0.1s
 => [2/2] COPY app/index.html /usr/share/nginx/html/index.html                                                                        0.1s
 => exporting to image                                                                                                                0.9s
 => => exporting layers                                                                                                               0.4s
 => => exporting manifest sha256:1566f6177bb2aca3f935402b8ee65ce6c84cb7da716deae6a0796a890d4c3848                                     0.1s
 => => exporting config sha256:e629d2260e24b4941d4775b813711755a0a42276ef85f81cab657cb450d94765                                       0.1s
 => => exporting attestation manifest sha256:bb8a3279f6764a1c25fe35638305ab520ac52706d0a63b5b6d3e4c0ff5d5e050                         0.1s
 => => exporting manifest list sha256:0481f1dc7214b3821472ccec93b09f39219abd56db9b3c9b2e875c8fc31de9f8                                0.1s
 => => naming to docker.io/library/codyssey_01-web:latest                                                                             0.0s
 => => unpacking to docker.io/library/codyssey_01-web:latest                                                                          0.1s
 => resolving provenance for metadata file                                                                                            0.0s
[+] up 1/2
[+] up 2/3
[+] up 3/3
 ✔ Network codyssey_01_default Created                                                                                                 0.1
s
 ✔ Container codyssey_01-web-1 Started                                                                                                 1.0s
NAME                IMAGE             COMMAND                   SERVICE   CREATED         STATUS                  PORTS
codyssey_01-web-1   codyssey_01-web   "/docker-entrypoint.…"   web       2 seconds ago   Up Less than a second   127.0.0.1:8081->8085/tcp
HTTP/1.1 200 OK
Server: nginx/1.31.8
Date: Mon, 09 Nov 2026 08:06:02 GMT
Content-Type: text/html
Content-Length: 33
Last-Modified: Sun, 08 Nov 2026 10:39:04 GMT
Connection: keep-alive
ETag: "6af05148-21"
Accept-Ranges: bytes

﻿<h1>Bind Mount Success!</h1>
web-1  | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
web-1  | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
web-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
web-1  | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
web-1  | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
web-1  | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
web-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
web-1  | 20-envsubst-on-templates.sh: Running envsubst on /etc/nginx/templates/default.conf.template to /etc/nginx/conf.d/default.conf
web-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
web-1  | /docker-entrypoint.sh: Configuration complete; ready for start up
web-1  | 2026/11/09 08:06:02 [notice] 1#1: using the "epoll" event method
web-1  | 2026/11/09 08:06:02 [notice] 1#1: nginx/1.31.8
web-1  | 2026/11/09 08:06:02 [notice] 1#1: built by gcc 15.2.0 (Alpine 15.2.0)
web-1  | 2026/11/09 08:06:02 [notice] 1#1: OS: Linux 6.18.40.1-microsoft-standard-WSL2
web-1  | 2026/11/09 08:06:02 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker processes
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 36
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 37
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 38
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 39
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 40
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 41
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 42
web-1  | 2026/11/09 08:06:02 [notice] 1#1: start worker process 43
web-1  | 172.18.0.1 - - [09/Nov/2026:08:06:02 +0000] "GET / HTTP/1.1" 200 33 "-" "curl/8.13.0" "-"
```
<img width="669" height="372" alt="Compose 단일 서비스" src="https://github.com/user-attachments/assets/06f8ff45-b87f-4fc3-8a5e-8b0271c8132b" />
----

### Compose 멀티 컨테이너
- web 컨테이너에서 helper라는 서비스 이름으로 HTTP 통신했음
```text
PS C:\Users\KJH\source\Codyssey_01> @'
>>
>>   helper:
>>     image: nginx:alpine
>> '@ | Add-Content .\docker-compose.yml -Encoding ascii
PS C:\Users\KJH\source\Codyssey_01> docker compose config
>> docker compose up -d
>> docker compose ps
name: codyssey_01
services:
  helper:
    image: nginx:alpine
    networks:
      default: null
  web:
    environment:
      NGINX_PORT: "8085"
    networks:
      default: null
    volumes:
      - type: bind
        source: C:\Users\KJH\source\Codyssey_01\WebServer\templates\default.conf.template
        target: /etc/nginx/templates/default.conf.template
        read_only: true
        bind: {}
    build:
      context: C:\Users\KJH\source\Codyssey_01\WebServer
      dockerfile: Dockerfile
    ports:
      - mode: ingress
        host_ip: 127.0.0.1
        target: 8085
        published: "8081"
        protocol: tcp
networks:
  default:
    name: codyssey_01_default
[+] up 1/2
[+] up 2/2
[+] up 2/2
 ✔ Container codyssey_01-helper-1 Created                                                                                              0.2
 ✔ Container codyssey_01-helper-1 Started                                                                                              0.7s
NAME                   IMAGE             COMMAND                   SERVICE   CREATED         STATUS                  PORTS
codyssey_01-helper-1   nginx:alpine      "/docker-entrypoint.…"   helper    1 second ago    Up Less than a second   80/tcp
codyssey_01-web-1      codyssey_01-web   "/docker-entrypoint.…"   web       4 minutes ago   Up 4 minutes            127.0.0.1:8081->8085/tcp
PS C:\Users\KJH\source\Codyssey_01> docker compose exec web wget -qO- http://helper:80
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, nginx is successfully installed and working.
Further configuration is required for the web server, reverse proxy,
API gateway, load balancer, content cache, or other features.</p>

<p>For online documentation and support please refer to
<a href="https://nginx.org/">nginx.org</a>.<br/>
To engage with the community please visit
<a href="https://community.nginx.org/">community.nginx.org</a>.<br/>
For enterprise grade support, professional services, additional
security features and capabilities please refer to
<a href="https://f5.com/nginx">f5.com/nginx</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```
----

### 환경 변수 활용
- NGINX_PORT 환경 변수로 컨테이너 내부 서버 포트를 8085에서 8095로 변경했다.
- NGINX 설정 파일의 listen 값과 docker compose ps의 포트 매핑으로 변경을 확인했다.
- 호스트 접속 포트는 8081로 유지했으며, 변경 후에도 HTTP 200 OK 응답을 확인했다.
- 검증 후 환경 변수를 제거하고 컨테이너를 재생성하여 기본 포트 8085로 복원했다.
  
```text
PS C:\Users\KJH\source\Codyssey_01> Set-Location "$env:USERPROFILE\source\Codyssey_01"
PS C:\Users\KJH\source\Codyssey_01> docker compose exec web cat /etc/nginx/conf.d/default.conf
server {
    listen 8085;
    server_name localhost;

    location / {
        root /usr/share/nginx/html;
        index index.html;
    }
}
PS C:\Users\KJH\source\Codyssey_01> $env:NGINX_PORT = "8095"
PS C:\Users\KJH\source\Codyssey_01> docker compose --progress plain up -d web
 Container codyssey_01-web-1 Recreate
 Container codyssey_01-web-1 Recreated
 Container codyssey_01-web-1 Starting
 Container codyssey_01-web-1 Started
PS C:\Users\KJH\source\Codyssey_01> docker compose ps
NAME                   IMAGE             COMMAND                   SERVICE   CREATED          STATUS          PORTS
codyssey_01-helper-1   nginx:alpine      "/docker-entrypoint.…"   helper    11 minutes ago   Up 11 minutes   80/tcp
codyssey_01-web-1      codyssey_01-web   "/docker-entrypoint.…"   web       10 seconds ago   Up 8 seconds    127.0.0.1:8081->8095/tcp
PS C:\Users\KJH\source\Codyssey_01> docker compose exec web cat /etc/nginx/conf.d/default.conf
server {
    listen 8095;
    server_name localhost;

    location / {
        root /usr/share/nginx/html;
        index index.html;
    }
}
PS C:\Users\KJH\source\Codyssey_01> curl.exe -i http://localhost:8081
HTTP/1.1 200 OK
Server: nginx/1.31.8
Date: Mon, 09 Nov 2026 08:52:35 GMT
Content-Type: text/html
Content-Length: 33
Last-Modified: Sun, 08 Nov 2026 10:39:04 GMT
Connection: keep-alive
ETag: "6af05148-21"
Accept-Ranges: bytes

﻿<h1>Bind Mount Success!</h1>
PS C:\Users\KJH\source\Codyssey_01> Remove-Item Env:NGINX_PORT
PS C:\Users\KJH\source\Codyssey_01> docker compose --progress plain up -d web
 Container codyssey_01-web-1 Recreate
 Container codyssey_01-web-1 Recreated
 Container codyssey_01-web-1 Starting
 Container codyssey_01-web-1 Started
PS C:\Users\KJH\source\Codyssey_01> docker compose ps
NAME                   IMAGE             COMMAND                   SERVICE   CREATED          STATUS          PORTS
codyssey_01-helper-1   nginx:alpine      "/docker-entrypoint.…"   helper    12 minutes ago   Up 12 minutes   80/tcp
codyssey_01-web-1      codyssey_01-web   "/docker-entrypoint.…"   web       7 seconds ago    Up 6 seconds    127.0.0.1:8081->8085/tcp
```
----

### Compose 운영 명령
| 명령 | 확인한 내용 |
|---|---|
| `up -d` | 서비스를 백그라운드로 실행 |
| `ps` | 실행 상태와 포트 확인 |
| `logs` | 서버 시작·접속 로그 확인 |
| `down` | Compose 컨테이너와 기본 네트워크 제거 |
| 다시 `up -d` | 같은 설정으로 재실행 |

```text
PS C:\Users\KJH\source\Codyssey_01> curl.exe -i http://localhost:8081
>> docker compose ps
>> docker compose logs --tail 30
>>
>> docker compose down
>> docker compose ps -a
>>
>> docker compose up -d
>> docker compose ps
HTTP/1.1 200 OK
Server: nginx/1.31.8
Date: Mon, 09 Nov 2026 08:40:56 GMT
Content-Type: text/html
Content-Length: 33
Last-Modified: Sun, 08 Nov 2026 10:39:04 GMT
Connection: keep-alive
ETag: "6af05148-21"
Accept-Ranges: bytes

﻿<h1>Bind Mount Success!</h1>
NAME                   IMAGE             COMMAND                   SERVICE   CREATED          STATUS          PORTS
codyssey_01-helper-1   nginx:alpine      "/docker-entrypoint.…"   helper    30 minutes ago   Up 30 minutes   80/tcp
codyssey_01-web-1      codyssey_01-web   "/docker-entrypoint.…"   web       15 minutes ago   Up 15 minutes   127.0.0.1:8081->8085/tcp
helper-1  | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
helper-1  | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
helper-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
helper-1  | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
helper-1  | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
web-1     | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
helper-1  | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
web-1     | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
web-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
web-1     | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
web-1     | 10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
web-1     | /docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
web-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
helper-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
helper-1  | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
web-1     | 20-envsubst-on-templates.sh: Running envsubst on /etc/nginx/templates/default.conf.template to /etc/nginx/conf.d/default.conf
web-1     | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
web-1     | /docker-entrypoint.sh: Configuration complete; ready for start up
web-1     | 2026/11/09 08:25:19 [notice] 1#1: using the "epoll" event method
web-1     | 2026/11/09 08:25:19 [notice] 1#1: nginx/1.31.8
web-1     | 2026/11/09 08:25:19 [notice] 1#1: built by gcc 15.2.0 (Alpine 15.2.0)
web-1     | 2026/11/09 08:25:19 [notice] 1#1: OS: Linux 6.18.40.1-microsoft-standard-WSL2
web-1     | 2026/11/09 08:25:19 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker processes
helper-1  | /docker-entrypoint.sh: Configuration complete; ready for start up
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 36
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: using the "epoll" event method
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 37
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 38
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 39
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 40
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 41
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 42
web-1     | 2026/11/09 08:25:19 [notice] 1#1: start worker process 43
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: nginx/1.31.8
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: built by gcc 15.2.0 (Alpine 15.2.0)
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: OS: Linux 6.18.40.1-microsoft-standard-WSL2
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker processes
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 30
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 31
web-1     | 172.18.0.1 - - [09/Nov/2026:08:40:56 +0000] "GET / HTTP/1.1" 200 33 "-" "curl/8.13.0" "-"
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 32
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 33
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 34
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 35
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 36
helper-1  | 2026/11/09 08:10:13 [notice] 1#1: start worker process 37
helper-1  | 172.18.0.2 - - [09/Nov/2026:08:10:33 +0000] "GET / HTTP/1.1" 200 896 "-" "Wget" "-"
[+] down 2/3
 ✔ Container codyssey_01-web-1    Removed                                                                                              0.7[+] down 3/3
 ✔ Container codyssey_01-helper-1 Removed                                                                                              0.7
s
 ✔ Network codyssey_01_default    Removed                                                                                              0.2s
NAME      IMAGE     COMMAND   SERVICE   CREATED   STATUS    PORTS
[+] up 1/3
[+] up 3/3
s
[+] up 2/3
[+] up 3/3
 - Container codyssey_01-web-1    Starting                                                                                             0.9s
 ✔ Container codyssey_01-web-1    Started                                                                                              1.3s

NAME                   IMAGE             COMMAND                   SERVICE   CREATED        STATUS                  PORTS
codyssey_01-helper-1   nginx:alpine      "/docker-entrypoint.…"   helper    1 second ago   Up 1 second             80/tcp
codyssey_01-web-1      codyssey_01-web   "/docker-entrypoint.…"   web       1 second ago   Up Less than a second   127.0.0.1:8081->8085/tcp
```

### GitHub 업로드
```text
PS C:\Users\KJH\source\Codyssey_01> git commit -m "Add Compose configuration and NGINX template"
>> git push origin main
>> git status
[main f48d144] Add Compose configuration and NGINX template
 2 files changed, 21 insertions(+)
 create mode 100644 WebServer/templates/default.conf.template
 create mode 100644 docker-compose.yml
To https://github.com/KMJ-lroise/Codyssey_01.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/KMJ-lroise/Codyssey_01.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
PS C:\Users\KJH\source\Codyssey_01> git pull --rebase origin main
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (6/6), 5.78 KiB | 88.00 KiB/s, done.
From https://github.com/KMJ-lroise/Codyssey_01
 * branch            main       -> FETCH_HEAD
   8578a38..3d0a685  main       -> origin/main
Successfully rebased and updated refs/heads/main.
PS C:\Users\KJH\source\Codyssey_01> git push origin main
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 837 bytes | 279.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/KMJ-lroise/Codyssey_01.git
   3d0a685..f0be616  main -> main
PS C:\Users\KJH\source\Codyssey_01> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

### GitHub SSH 인증 설정 및 SSH 인증 확인
- Ed25519 방식의 SSH 키를 생성했다.
- 공개키 파일(id_ed25519.pub)을 GitHub 계정의 SSH keys에 등록했다.
- GitHub 서버의 ED25519 지문을 공식 값과 대조한 뒤 연결했다.
- ssh -T 명령으로 GitHub 계정 인증 성공을 확인했다.
- 개인키와 passphrase는 저장소 및 문서에 포함하지 않았다.

```text
PS C:\Users\KJH\source\Codyssey_01> Get-ChildItem "$env:USERPROFILE\.ssh" -ErrorAction SilentlyContinue
PS C:\Users\KJH\source\Codyssey_01> ssh-keygen -t ed25519 -C "codyssey-laptop"
Generating public/private ed25519 key pair.
Enter file in which to save the key (C:\Users\KJH/.ssh/id_ed25519):
Created directory 'C:\\Users\\KJH/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\KJH/.ssh/id_ed25519
Your public key has been saved in C:\Users\KJH/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:NgMp3aWzBC8F397VUu4jyvmsAmtZ5YoHGeZAvyrAGQY codyssey-laptop
The key's randomart image is:
+--[ED25519 256]--+
|      o.. .     .|
|E    o B +     + |
|.   o * B .   o o|
| o   o B + o . o |
|o o   + S + .. ..|
| +     B +..o . .|
|  .   . B .+     |
|   . . = +  o    |
|    . . . ...o   |
+----[SHA256]-----+
PS C:\Users\KJH\source\Codyssey_01> Get-Content "$env:USERPROFILE\.ssh\id_ed25519.pub" | Set-Clipboard
PS C:\Users\KJH\source\Codyssey_01> Get-Content "$env:USERPROFILE\.ssh\id_ed25519.pub" | Set-Clipboard
PS C:\Users\KJH\source\Codyssey_01> ssh -T git@github.com
The authenticity of host 'github.com (20.200.245.247)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Enter passphrase for key 'C:\Users\KJH/.ssh/id_ed25519':
Hi KMJ-lroise! You've successfully authenticated, but GitHub does not provide shell access.
```
<img width="580" height="319" alt="ssh key" src="https://github.com/user-attachments/assets/d90c1e57-a6ed-4696-aa59-835f05961ff0" />

#### SSH 인증 확인

```text
PS C:\Users\KJH\source\Codyssey_01> ssh -T git@github.com
The authenticity of host 'github.com (20.200.245.247)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Enter passphrase for key 'C:\Users\KJH/.ssh/id_ed25519':
Hi KMJ-lroise! You've successfully authenticated, but GitHub does not provide shell access.
```
----





