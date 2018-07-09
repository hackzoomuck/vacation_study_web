# vacation_study_web
		- Node.js 
서버 사이드 - 네트워크의 한 방식인 클라이언트-서버 구조의 서버 쪽에서 행해지는 처리를 말한다.
npm - Node.js를 위한 패키지 관리 도구, 간단하게 라이브러리(모듈)를 설치 
SSH - Secure Shell은 네트워크 상의 다른 컴퓨터에 로그인하거나 원격 시스템에서 명령을 실행하고 다른 시스템으로 파일을 복사할 수 있도록 해 주는 api 또는 그 protocol을 가리킨다.

		- npm
로컬 모듈 설치
	npm install request
	
	//모듈을 읽어 들이기
	const fs  = require('fs')
	const request = require('request')
	
	//request 모듈을 사용해 파일을 다운로드
	request('http://') .pipe(fs.createWriteStream('test.png'))
	
	//명령줄에서 명령어를 실행
	node request-downloadfile.js
	
전역 설치
	- 머신 전체에서 공유할 수 있는 도구 또는 라이브러리를 설치할 때 사용. 설치한 모듈은 특정 디렉토리에 설치됨.
	//npm으로 전역 모듈을 설치할 때 어떤 디렉토리에 설치되는지 알고 싶을 때 다음 명령어 사용
	npm root -g
	
	//스크립트 언어인 커피스크립트를 설치하고 싶을 때 명령어
	npm install -g coffee-script
	//coffee로 명령어를 실행 -e 옵션을 붙여서 커피스크립트 코드를 곧바로 실행
	coffee -e "console.log num for num in [5..1]"
	
npm으로 설치한 모듈을 참조할 수 없는 경우
	- 전역 모듈의 디렉토리 경로가 제대로 잡혀 있지 않을 때 발생하는 문제, NODE_PATH 환경 변수에 npm의 전역 경로를 추가해서 문제를 해결)
	//우분투의 경우 홈 디렉토리에 있는 ~/.bashrc에 NODE_PATH 환경 변수를 추가.
	echo export NODE_PATH=$(npm root -g) >> ~/.bashrc
	source ~/.bashrc
	
모듈 제거
	//npm uninstall 모듈이름
	npm uninstall request

npm을 사용한 프로젝트 생성 방법
	//디렉토리 생성
	mkdir project_a
	cd project_a
	//npm으로 프로젝트를 생성
	npm init
	- 이름 버전 설명 들의 정보를 설정 후 최종적으로 "is this ok"라고 물음. enter 하면 "package.json"이라는 파일이 만들어짐.
	"package.json"은 npm으로 프로젝트를 관리하기 위한 전용 설정 파일.
	- package.json으로 모듈 설치 기록하기
	프로젝트에서 사용할 라이브러리를 npm으로 설치 할 때 "--save" 또는 "-S" 옵션을 붙여서 설치하면 package.json에 의존 모듈로써 설치한 모듈과 버전이 기록됨.
	//예시로 "colors"라는 라이브러리를 설치
	npm install colors --save
	그리고 package.json을 열어보면 dependencies라는 항목이 추가되어 있고, 해당 파일 내부에 모듈과 버전이 적혀 있음.
