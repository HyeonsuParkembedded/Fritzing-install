# Fritzing-install

이 저장소는 Windows 환경에서 Fritzing 1.x를 빌드하기 위한 배치 스크립트를 제공합니다.
각 배치 파일은 필요한 도구 다운로드부터 소스 코드 빌드, 배포용 패키지 생성까지
전체 과정을 단계별로 자동화합니다.

## 사용 방법
1. **스크립트 다운로드**
   - `00_Download_Script.bat`을 실행하여 빌드 스크립트와 부가 프로그램을 다운로드합니다.
2. **전체 빌드 실행**
   - `00_Execute_Script.bat`을 관리자 권한으로 실행하면 다음 단계가 순차적으로 진행됩니다.
     1. 필요한 파일 다운로드 및 압축 해제
     2. Qt 6.5.3 설치
     3. Visual Studio Build Tools 2019 설치
     4. 의존 라이브러리(Boost, libgit2, zlib 등) 빌드
     5. Fritzing 소스 및 파트 라이브러리 다운로드
     6. Fritzing 컴파일 및 실행 파일 생성
     7. 필요 DLL 복사 및 정리 후 ZIP 패키지 생성

빌드가 완료되면 `release64` 폴더에 완성된 Fritzing 실행 파일과 관련 DLL이 생성되며,
`20_Create_Fritzing_zip_package.bat`에서 최종 배포용 ZIP 파일을 만듭니다.

각 스크립트는 Windows 10/11 64비트 환경을 기준으로 작성되었으며,
인터넷 연결과 충분한 디스크 공간이 필요합니다.
