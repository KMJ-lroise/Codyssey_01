# Codyssey_01

# 설치 명령 실행 및 설치 과정 확인
# 가상 머신 플랫폼 활성화 완료 메시지 확인
# 재부팅 전 wsl --status에서 미설치로 표시되는 현상 확인
# 교육장 PC의 초기화 환경으로 인해 재부팅은 보류

PS C:\WINDOWS\system32> wsl --status
Linux용 Windows 하위 시스템 설치되어 있지 않습니다. 'wsl.exe --install'을 실행하여 설치할 수 있습니다.
자세한 내용은 https://aka.ms/wslinstall
 참조하세요.

<img width="872" height="627" alt="02_wsl_status" src="https://github.com/user-attachments/assets/d323acbd-4c60-4320-bf93-777c5470add1" />


# Docker와 Git은 명령어를 찾을 수 없었고, VS Code 1.144.1은 확인됐다고 기록

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

<img width="876" height="610" alt="03_program_check" src="https://github.com/user-attachments/assets/24195567-6db4-44b5-9995-aa8c5b51bf6f" />


# Get-Location 입력 : 현재 내가 어느 폴더에 있는지 명령어를 입력하여 확인.

PS C:\Users\User> Get-Location

Path
----
C:\Users\User


# Get-ChildItem 입력 : 현재 있는 폴더 안에 어떤 폴더와 파일들이 있는지 알려주는 명령어를 입력하여 확인.

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



