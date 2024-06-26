### VPC란 무엇인가
- 사용자의 AWS 계정 전용 가상 네트워크
- 즉, 가상으로 존재하는 데이터 센터
- 외부에 격리된 컨테이너 구성 가능
	- 원하는 대로 사설망을 구축 가능
		- 부여된 IP대역을 분할하여 사용 가능
- 리전 단위
### VPC 사용 사례
- EC2m RDS, Lambda 등의 AWS 컴퓨팅 서비스 실행
- 다양한 서브넷 구성
- 보안 설정 (IP BLock, 인터넷에 노출안되는 EC2 구축)

### VPC 구성 요소
- 서브넷
- 인터넷 게이트웨이
- NACL/보안그룹
- 라우트 테이블
- NAT Instance/NAT Gateway
- Bastion Host
- VPC Endpoint

### 서브넷이란?
 - VPC의 하위 단위로, 할당된 IP를 더 분할한 개념
- 하나의 서브넷은 하나의 AZ안에 위치
- CIDR block range로 IP주소 지정
- AWS 서브넷의 예약 IP
	- 0 : 네트워크 어드레스
	- 1 : VPC Router
	- 2 : DNS Server
	- 3 : 미래에 사용을 위해 남겨둠
	- 255 :브로드캐스트 어드레스 (근데 지원안함 AWS에서)
- 서브넷의 종류
	- 퍼블릿 서브넷 : 외부에서 인터넷을 통해 연결 가능
		- IGW를 통해 인터넷과 연결
		- 안에 위치한 인스턴스에 퍼블릿 IP 부여 가능
		- 웹서버 등 유저에게 노출되어야 하는 인프라
	- 프라이빗 서브넷 : 외부에서 인터넷을 통해 연결 불가
		- 외부 인터넷으로 경로가 없음
		- 데이터베이스, 로직서버 등 외부에 노출 될 필요가 없는 인프라

### 인터넷 게이트웨이
- VPC가 외부의 인터넷과 통신할 수 있도록 경로 만들어주는 리소스
- IPv4, IPv6 지원
	- IPv4의 경우 NAT 역할
-  Route Table에서 경로 설정 후에 접근 가능
- 무료
