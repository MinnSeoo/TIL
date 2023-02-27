### **02-3 기본 네트워크 환경 구성(VPC / Subnet / Internet Gateway / Rout Table)**

1. **[VPC 생성]**
    - VPC 생성 클릭
    - 이름 지정 (lab-vpc)
    - ipv4 CIDR 할당
    - 나머지 default → 생성
    - 생성된 VPC 선택 → 오른쪽 마우스 → VPC 설정 편집 → DNS 확인 활성화✅
    
2. **[서브넷 생성]**
    - Public subnet 2개 생성(가용 영역을 다르게 설정함 a:1개, c:1개)
        
        (lPv4 CIDR은 VPC의 IPv4 ClDR보다 작게 설정해야함)
        
    - Private subnet 4개 생성(가용영역 - a: 2개, c: 2개)
    
3. **[인터넷 게이트웨이 생성]**
    - 이름 지정 후 생성
    - 위에서 생성한 igw에 1번에서 생성한 vpc를 꼭 연결시켜줘야함!

1. **[라우팅 테이블 생성]**
    - public-rtb 1개 생성
    - 위에서 생성한 public-rt 라우팅 편집(대상 : 0.0.0.0/0,위에서 생성한 igw 선택)
    - private-rtb 4개생성(각각 지정해줌)
    
    ```
    public subnet 과 private subnet의 차이는 ? ? ?
    -> public subnet rtb 같은 경우는 igw을 통해서 트래픽이 외부로 
    	 나갈 수 있어 외부와 통신이 가능하다.
    
    	 private subnt rtb 같은 경우는 igw의 경로를 설정하지 않았기 때문에
    	 외부와 통신이 불가능하다. 
    ```
    