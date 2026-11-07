# Codyssey_01

## 1. 설치 명령 실행 및 설치 과정 확인
- 가상 머신 플랫폼 활성화 완료 메시지 확인
- 재부팅 전 wsl --status에서 미설치로 표시되는 현상 확인

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


## 3. Get-Location 입력 
- 현재 내가 어느 폴더에 있는지 명령어를 입력하여 확인.

PS C:\Users\User> Get-Location

Path
----
C:\Users\User


## 4. Get-ChildItem 입력 
- 현재 있는 폴더 안에 어떤 폴더와 파일들이 있는지 알려주는 명령어를 입력하여 확인.

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

<img width="597" height="592" alt="04_terminal_basic" src="https://github.com/user-attachments/assets/0bc3f3af-3937-495b-b823-2e74e1a37ce4" />


## 5. 폴더 생성 및 이동

PS C:\Users\User> cd Desktop
PS C:\Users\User\Desktop> Get-Location

Path
----
C:\Users\User\Desktop

<img width="361" height="117" alt="05_folder_navigation" src="https://github.com/user-attachments/assets/34e328d5-01a0-409d-93ac-ba0dbb2d80a3" />


## 6. 파일 생성 및 관리
- PowerShell에서 폴더와 파일을 만들고, 내용을 입력하고, 확인하고, 복사하고, 삭제.
-  '-'를 입력해야 하는데 '_'를 입력하여 오류 발생 -> '-'로 다시 입력하여 문제 해결

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

<img width="887" height="317" alt="06_file_management_02" src="https://github.com/user-attachments/assets/efb88d44-dbf9-489f-9f29-0fa5ee0001a2" />
<img width="921" height="967" alt="06_file_management_01" src="https://github.com/user-attachments/assets/5c142096-1a43-4d5c-8ca9-34101e6801fd" />


## 7. 파일 권한 확인 및 변경
- 파일을 누가 읽고, 수정하고, 실행할 수 있는지 정함.

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

<img width="762" height="981" alt="07_file_permissions_01" src="https://github.com/user-attachments/assets/cb778f62-3646-4e92-83b2-26824877ad7f" />


## 8. Docker 설치 및 환경 확인





## 9. Docker 컨테이너 실행 및 관리

## 10. Dockerfile 작성 및 웹 서버 실행

## 11. 포트 포워딩

## 12. Bind Mount

## 13. Docker Volume 및 데이터 유지

## 14. Git 및 GitHub 연동

## 15. 트러블슈팅

## 16. 최종 결과





