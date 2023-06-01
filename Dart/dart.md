# Dart

https://dartpad.dev 로 다운로드없이 dart를 사용할 수 있다.

Flutter를 사용하기 전에 배워야하는 언어이다.
UI를 만드는 것에 최적화되어있고, 모든 플랫폼에서 빠르다.

두가지 컴파일러가 있는데 Dart web과 Dart Native가 있다.
Dart web은 dart로 쓴 코드를 javascript로 변환해주고, Dart Native는 코드를 CPU의 아키텍쳐에 맞게 변환해준다. 모바일 폰에서 사용하는 ARM64로도 가능하고, 데스크탑용으로도 가능하다.
JIT(Just In Time)컴파일러와 AOT(Ahead Of Time)컴파일러 두가지를 다 가지고 있다.

\*JIT(Just In Time)컴파일러와 AOT(Ahead Of Time)이 있는데 JOT는 즉각적으로 화면으로 변화를 볼 수 있어서 좋다.

AOT는 눈으로 확인하고 싶을 때 마다 전체 프로젝트를 컴파일을 해줘야하기때문에 빌드할 때만 사용하는게 좋다.

<br/>

# 설치 방법

vscode에서 Dart를 사용하기 위해서는 우선 Chocolatey를 설치해야한다.

<br/>

## Chocolatey란?

Chocolatey (약칭 Choco) : 윈도우에서 사용할 수 있는 커맨드 라인 패키지 매니저

<br/>

## Chocolatey 설치 방법

1.  실행창(window + r)에 cmd를 적고, ctrl+shift+enter를 쳐서 커맨드창을 관리자모드로 킨다.
2.  아래 코드로 install

        Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

<br/>

- 'Set-ExecutionPolicy'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는
  배치 파일이 아닙니다. 문구가 나오면 아래의 명령어 적용

        @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

3. 설치완료 후 choco 입력해서 버전확인

<br/>

## Dart 설치 방법

    choco install dart-sdk

1.  Y 입력
2.          dart --version 으로 SDK설치가 잘 되었는지 확인

vscode에서 Dart 익스텐션을 받아준다.
