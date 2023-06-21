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

여기서, "1-7    10c4:ea60  Silicon Labs CP210x USB to UART Bridge(COM6)" 이 Lidar가 연결된 USB 포트이다.

 PowerShell에 usbipd wsl attach --busid 1-7 명령을 실행해서 wsl에 USB를 연결한다.(이때 꼭 다른 PowerShell에서 wsl이 실행되고 있어야 한다.)
 
![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/7390094a-5081-4611-853e-be5ccbe3df2f)

먼저 열었던 PowerShell의 wsl 창에서 lsusb 명령을 실행하여 가상 linux에서 usb 장치가 보이는지 확인한다.

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/f1708c2e-89bb-46e7-a6ba-b0066810ae8a)

USB 연결을 끊을 때는 usbipd wsl detach --busid 1-7 명령을 실행한다.

(4) ROS2 실행

ROS2의 RPLidar 페이지로 간다. -> http://wiki.ros.org/rplidar

먼저 ttyUSB를 확인하고 읽고 쓰기 권한을 부여한다.

![image](https://github.com/kutmslee/ROS2-Lidar-WSL/assets/38107813/b0ad2b9b-e545-4700-8b46-11b3fb8dff41)

. ~/ros2_humble/install/local_setup.bash 실행하고

ros2 launch rplidar_ros view_rplidar.launch.py 실행한다.

Lidar가 연결된 USB포트는 rplidar.launch.py 에서 변경 가능하다.

moses@DESKTOP-Q1B8HR9:~/ros2_humble/src/rplidar_ros2/launch$ nano rplidar.launch.py
