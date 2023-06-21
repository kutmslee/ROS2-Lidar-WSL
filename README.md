# ROS2-Lidar-WSL
(1) WSL 설치

(2) winget 없으면 설치

구글에서 winget 검색

https://learn.microsoft.com/ko-kr/windows/package-manager/winget/

winget 미리 보기 버전 설치 [개발자 전용] - "최신 winget 미리 보기 버전을 다운로드합니다" -> 여기를 클릭해서 winget 다운로드하고 설치

(3) USB/IP 설치

구글에서 usbipd 검색

https://learn.microsoft.com/ko-kr/windows/wsl/connect-usb

Windows PowerShell(관리자) 실행

페이지 중간쯤 있는 참고 부분에서 usbipd-win 설치 명령 복사해서

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/a213569b-990c-49cd-8c24-aa112199b299)

PowerShell에서 실행

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/fb42fd89-20a0-4b36-a146-7b46cf20bddf)

다 되면 다 됬다고 뜸

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/06d67213-676a-427e-91e2-cde97ef6aa86)

Windows10의 서비스에서 확인가능

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/d486c997-b479-4e95-9e05-72e5785d3b72)

PowerShell에서 wsl 실행하고 Microsoft의 "USB 디바이스 연결" 설명서에서 hwdata 설치 명령 복사해서 실행

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/af0cec24-20df-4153-a839-b4f6035b45cd)

PowerShell에서 wsl를 끄지 말고 PowerShell을 관리자 권한으로 하나 더 연다.

Lidar의 USB커넥터를 PC에 꽂고 새로 연 PowerShell에서 usbipd wsl list 명령 실행

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/b063c09b-e2ea-4a47-9ef4-945da546ccc6)


