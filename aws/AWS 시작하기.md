- AWS를 처음 가입하면 루트유저가 생성된다
	- 루트유저란?
		- 생성한 계정의 모든 권한 자동으로 가짐
		- 생성시 만든 이메일 주소로 로그인
		- 탈취당했을 때 복구가 힘듬 : 사용자제해야함
		- 루트유저는 관리용으로만 이용해야한다
		- AWS API 호출 불가 : AccessKey, SecetAccessKey 부여 불가
	- 일반적으로 사용할 때는 IAM User로 사용해야함
		- IAM User?
			- IAM을 통해 생성한 유저
			- 만들 떄 주어진 아이디로 로그인
			- 처음에 기본 권한이 없어서 따로 권한 부여해야함
			- AWS API호출 가능
		- 탈취당했을 때 그냥 IAM유저 삭제하면 끝
		- 빌링관련한 부분은 IAM유저에서 못건드리게 할 수 있음
- AWS 초기 설정
	- 리전 선택하기(서울)
	- 보안 자격 증명 탭
		- 멀티팩터인증(MFA) 활성화 (가상MFA디바이스)
			- QR코드 이미지 안전한곳에 저장
				- 안하면 핸드폰 잃어버렸을 때 상당히 곤란해짐
	- IAM대시보드
		- 계정 별칭 생성으로 별칭 생성
			- 별칭에 따라 IAM사용자의 로그인 URL이 생성되므로 필요한 절차
			- IAM으로 로그인할 때 별칭으로 로그인함
		- 사용자탭에서 사용자추가
			- 이름, 액세스 유형 설정
			- 권한 설정
				- 기존 정책 직접 연결
					- AdministratorAccess
						- 빌링권한만 빼고 전부 허용
						- 결제 대시보드만 빼고 접근 가능
			- 액세스키와 비밀 액세스키 CSV파일 다운로드
			- AdministratorAccess라면 여기도 MFA 활성화
