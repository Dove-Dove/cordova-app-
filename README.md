코르노바 앱 생성 + 설정
=================
1. JDK 설치    
    jdk-8u162-windows-x64.exe 버전 설치

2. \hybridapp 디렉토리 만들기   
    cmd에 들가기   
    /cd - > md hybridapp 순서로 파일 생성

3. 아파치 앤트 설치하기   
    c:\HybridApp\폴더에 gradle-3.5.zip 다운로드    
    알아서 풀기

4. 안드로이드 스튜디오 설치  
    안드로이드 스튜딛오 설치 후   
    가상 기계(AVD)는 "Nexus 5"나 "Nexus 5X" api 29 로 생성   
      
4. 1안드로이드 플랫폼 패키지 추가 설치하기   
SDK platforms   
	Android 12L	32   
	Android 12	31   
	Android 11	30   
	Android R	29   

SDK Tools   
	Android SDK Tools   
	Android SDK Platfor-tools   
	Android SDK Build-tools   

Extra   
	Android Support Repository  
	Android Auto Desktop head unit emulator  
	Android auto API simulator   
	Google Repository    
	Google USB Driver    
	Google Play Services   
	Android SDK Command-line Tools   
	Intel x86 Emulator Accelerator(HAXM installer)    

컴퓨터마다 없는경우도 있음 (있는것만 다운로드)

5. 환경 변수 설정하기(윈도우+x => 시스템=> 고급시스템설정)   
JAVA_HOME 	c:\progrqm files\java\jdk1.8--   
ANDROID_SDK_ROOT	C:\Users\608\AppData\Local\Android\android-sdk   
GRADLE_HOME	C:\gradle-3.5   

Path 
	%JAVA_HOME%\bin;   
	%ANDROID_HOME%\tools   
	%ANDROID_HOME%\platform-tools   
	%ANDROID_HOME%\build-tools   
	%ANDROID_HOME%\cmdline-tools\latest\bin   
	%ANDROID_HOME\emulator   
	%GRADLE_HOME%\bin   
	c:\HybridApp\apace-ant-1.9.16\bin   
    (C:\Program Files (x86)\Common Files\Oracle\Java\javapath)

6. Node.js 설치하기   
"node js 설치" 검색 후 다운로드   
node -v   
npm -v   
npm update -g   
복사 붙어넣기   

7. 폰갭(코르도바 설치하기)
npm install -g phonegap   
npm install -g cordova   
cordova -v   
npm update -g phonegap    
npm update -g cordova   

8. 안드로이드 코르도바 앱 만들기   
mkdir \HybridProject   
cd \HybridProject   
cordova create test com.example.test testApp -d   
cd test   
dir   
dir platform   
cordova platform add android    
dir platform   

9. Bundle Script -  build.gradle(:app) ->안드로이드 스튜디오   

-android 밑에 namespace 위에   
packagingOptions {   
        exclude 'META-INF/DEPENDENCIES.txt'   
        exclude 'META-INF/LICENSE.txt'  
        exclude 'META-INF/NOTICE.txt'   
        exclude 'META-INF/NOTICE'   
        exclude 'META-INF/LICENSE'   
        exclude 'META-INF/DEPENDENCIES'   
        exclude 'META-INF/notice.txt'   
        exclude 'META-INF/license.txt'  
        exclude 'META-INF/dependencies.txt'  
        exclude 'META-INF/LGPL2.1'   
    }   

10. App - Manifests -  AndroidManifest.xml   
-application 안에    
android:largeHeap="true" 넣기   

11. C:\Users\[사용자명]\.android 내에 있는 debug.keystore파일 삭제    
(삭제가 되지 않을 경우에는 Ctrl+Alt+Del => 작업관리자에서   
해당 프로세스 작업 끝내기 후에 삭제)   

12. Build - Clean Project   

13. 자신이 만든 프로젝트의 첫 번째 파일이름을 index.html로 변경   
CDN 방식을 Download 방식으로 변경   

	<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css"/>   
	<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>   
	<script src="http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js"></script>    
====>   

	<link rel="stylesheet" href="./css/jquery.mobile-1.4.5.min.css"/>   
	<script src="./js/jquery-1.11.1.min.js"></script>   
	<script src="./js/jquery.mobile-1.4.5.min.js"></script>   

아래에 아래의 코드 추가
<script src="cordova.js"></script>   


14. 프로젝트 폴더에 있는 모든 파일을 test폴더 아래에 있는 www 폴더로 복사

15. "삼성 usb 드라이버" 검색하여 파일 다운로드 및 설치

16. "USB 디버깅 설정 방법" 검색하여 폰을 usb 디버깅 상태로 설정

17. 컴퓨터와 폰 연결

18. AVD  실행 혹은 스마트폰 컴과 연결      
cordova run android --list   
cordova emulate android   
  (에뮬레이터에 실행)   
cordova run android   
  (기기에 실행)   

## 완료시 화면
<img src="/img/fSs.png" width="203px" height="403px" title="테스트" alt="fist"></img><br/>

## 자기소개 화면
<img src="/img/my.png" width="203px" height="403px" title="테스트" alt="my"></img><br/>