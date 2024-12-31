<ul>
<li><p><strong>가상화(virtualization)</strong></p>
<p>  물리적 하드웨어를 논리적으로 분리하여 여러 가상 환경을 하나의 물리적 시스템에서 동시에 운영할 수 있도록 해주는 기술. 이를 통해 IT 담당자들은 리소스의 효율적 관리, 서버의 통합, 비용 절감, 장애 대응 능력 향상 등을 이룰 수 있다.</p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/6dcbf6da-619a-420f-b49d-3f08bce41236/image.png" /></p>
</li>
</ul>
<pre><code>### 가상화의 주요 특징 및 장점:

1. **리소스 분리**: 물리적 하드웨어와 운영체제를 분리하여 여러 **가상 머신(Virtual Machine)**을 생성하고, 각각 독립적으로 운영체제와 응용 프로그램을 실행할 수 있습니다

### 가상 머신(Virtual Machine, VM)이란?

가상 머신은 **물리적 컴퓨터 위에 소프트웨어로 구현된 독립적인 컴퓨터 시스템**입니다. 

각 가상 머신은 독립된 운영체제와 응용 프로그램을 실행할 수 있으며, 실제 하드웨어와 분리되어 작동합니다. 가상 머신은 **하이퍼바이저(Hypervisor)**라는 소프트웨어를 통해 물리적 하드웨어 위에서 생성되고 관리됩니다.

**하이퍼바이저(Hypervisor)** 는 가상 머신(Virtual Machine, VM)을 생성하고 관리하는 소프트웨어 또는 **펌웨어 계층**입니다. 물리적 하드웨어 자원을 가상화하여 여러 운영체제와 애플리케이션을 동일한 하드웨어에서 동시에 실행할 수 있도록 합니다.

**펌웨어 계층**은 하드웨어와 소프트웨어 간의 중간에 위치하여, 하드웨어를 제어하고 소프트웨어가 하드웨어를 사용할 수 있도록 인터페이스를 제공하는 소프트웨어

1. **자원 효율성**: 여러 가상 시스템을 하나의 물리적 하드웨어에서 실행할 수 있어 자원을 효율적으로 활용하고, 하드웨어의 가용성을 극대화합니다.
2. **비용 절감**: 서버 가상화를 통해 물리적 서버 수를 줄여 운영 및 관리 비용을 절감할 수 있습니다.
3. **유연성**: 다양한 운영체제와 애플리케이션을 동시에 실행할 수 있으며, 서버와 네트워크 인프라를 유연하게 구성할 수 있습니다.
4. **비즈니스 연속성**: 가상 머신은 물리적인 하드웨어에 영향을 받지 않기 때문에 장애가 발생했을 때 다른 서버로 쉽게 마이그레이션하거나 복구할 수 있습니다.</code></pre><ul>
<li><p><strong>가상화 발전단계</strong></p>
<ol>
<li><strong>Gen 1: 클라이언트 하이퍼바이저 : 하이퍼바이저타입2 사용</strong> </li>
</ol>
<ul>
<li><strong>정의</strong>: 개별 컴퓨터(데스크톱 또는 랩톱)에서 하드웨어를 가상화하여 여러 운영체제를 실행하는 하이퍼바이저.</li>
<li><strong>특징</strong>:<ul>
<li>호스트형 하이퍼바이저(Type 2)를 주로 사용.</li>
<li>운영체제 위에서 실행되며, 가상 환경을 통해 애플리케이션 테스트 및 개발 용도로 활용.</li>
</ul>
</li>
<li><strong>예시</strong>:<ul>
<li>VMware Workstation, Oracle VirtualBox, Parallels Desktop.</li>
</ul>
</li>
<li><strong>한계</strong>:<ul>
<li>성능이 물리적 하드웨어에 비해 낮음.</li>
<li>주로 개인 사용자나 소규모 환경에서 활용.</li>
</ul>
</li>
</ul>
<ol>
<li><strong>Gen 2: 서버 하이퍼바이저 : 하이퍼바이저타입1 사용</strong> </li>
</ol>
<ul>
<li><p><strong>정의</strong>: 물리적 서버에서 직접 실행되는 하이퍼바이저를 통해 여러 가상 서버를 생성 및 관리.</p>
</li>
<li><p><strong>특징</strong>:</p>
<ul>
<li>네이티브 하이퍼바이저(Type 1)를 활용하여 성능 및 안정성 극대화.</li>
<li>데이터센터 및 서버 통합에 주로 사용.</li>
<li>하드웨어 리소스의 효율적 사용과 서버 통합을 통해 비용 절감.</li>
</ul>
</li>
<li><p><strong>예시</strong>:</p>
<ul>
<li>VMware ESXi, Microsoft Hyper-V, Xen, KVM.</li>
</ul>
</li>
<li><p><strong>영향</strong>:</p>
<ul>
<li><p>IT 인프라의 기본 단위가 물리적 서버에서 가상 서버로 변화.</p>
</li>
<li><p>하이퍼바이저는 <strong>타입 1</strong>과 <strong>타입 2</strong>로 나뉩니다.</p>
<h3 id="1-타입-1-type-1-네이티브-하이퍼바이저">1. <strong>타입 1 (Type 1)</strong>: 네이티브 하이퍼바이저</h3>
</li>
<li><p><strong>설명</strong>: 물리적 하드웨어 위에서 직접 실행됩니다. <strong>별도의 호스트 운영체제가 필요하지 않아</strong> &quot;베어메탈 하이퍼바이저&quot;라고도 불립니다.</p>
</li>
<li><p><strong>특징</strong>: 고성능, 안정성, 보안이 뛰어남.</p>
</li>
<li><p><strong>예시</strong>: VMware ESXi, Microsoft Hyper-V, Xen, KVM.</p>
<h3 id="2-타입-2-type-2-호스트형-하이퍼바이저">2. <strong>타입 2 (Type 2)</strong>: 호스트형 하이퍼바이저</h3>
</li>
<li><p><strong>설명</strong>: <strong>기존의 운영체제 위에서 실행</strong>됩니다. 하이퍼바이저가 응용 프로그램처럼 작동하며, 그 위에서 가상 머신을 실행합니다.</p>
</li>
<li><p><strong>특징</strong>: 설정과 사용이 간단하지만, 성능은 타입 1보다 떨어질 수 있음.</p>
</li>
<li><p><strong>예시</strong>: VMware Workstation, Oracle VirtualBox, Parallels Desktop.</p>
</li>
</ul>
</li>
</ul>
<ol>
<li><p><strong>Gen 3: 가상 인프라 : 소프트웨어 정의 데이터센터(SDDC) 개념이 등장.</strong></p>
</li>
<li><p><strong>Gen 4: 클라우드 :</strong>
물리적 하드웨어와 독립적인 완전한 <strong>가상 환경</strong> 제공.</p>
<h3 id="발전-단계-요약">발전 단계 요약:</h3>
</li>
<li><p><strong>Gen 1: 클라이언트 하이퍼바이저</strong> → 개인 환경에서 가상화 도입.</p>
</li>
<li><p><strong>Gen 2: 서버 하이퍼바이저</strong> → 데이터센터와 서버 통합.</p>
</li>
<li><p><strong>Gen 3: 가상 인프라</strong> → 데이터센터 전반의 자동화 및 통합.</p>
</li>
<li><p><strong>Gen 4: 클라우드</strong> → 가상화 기술이 클라우드 컴퓨팅으로 확장.</p>
</li>
</ol>
<ul>
<li><p><strong>정리를 하다보니 가상화기술과 클라우드컴퓨팅기술의 차이를 명확하게 하고싶었다.</strong></p>
</li>
<li><p><em>Gen 3: 가상 인프라*</em>는 <strong>기본적인 가상화 기술</strong>로 물리적 자원을 논리적으로 관리하며, 데이터센터 내에서의 자원 활용 최적화에 초점이 맞춰져 있습니다.</p>
</li>
<li><p><em>Gen 4: 클라우드*</em>는 이 가상화 기술을 <strong>네트워크와 결합</strong>하여, 글로벌 서비스 확장 및 온디맨드 제공과 같은 클라우드 컴퓨팅의 특성을 추가로 구현한 개념입니다.</p>
<p>→ <strong>즉, 가상화기술을 가지고 네트워크와 결합하여 구글드라이브와 같은 클라우드서비스를 제공해주는 것을 클라우드컴퓨팅 , 물리적자원을 논리적으로 관리할 수 있다는 기술이 가상화기술이다.</strong></p>
</li>
</ul>
</li>
</ul>
<ul>
<li><p><strong>클라우드 컴퓨팅이란?</strong></p>
<ul>
<li><p>인터넷을 통해 IT 리소스(컴퓨팅파워,스토리지, DB등)를  원할때 언제든지(On-demand) 제공하고 사용한 만큼만 비용을 지불하는 서비스</p>
</li>
<li><p><em>→ 주변에서 클라우드 컴퓨팅을 느낄 수 있는 것 = 구글 드라이브*</em> </p>
</li>
</ul>
</li>
<li><p><strong>CPU , 메모리 리소스 공유</strong></p>
<ul>
<li><strong>CPU 공유</strong></li>
</ul>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/3aabdca4-6ee4-4c5d-8d7d-af846127eaea/image.png" /></p>
<pre><code>- **메모리 리소스 공유**:
    - 가상 머신은 자신에게 할당된 메모리만 사용.
    - 필요에 따라 동적으로 메모리 크기가 변경될 수도 있음(하이퍼바이저에 따라 다름).</code></pre><ul>
<li><strong>가상 네트워킹: 이더넷 어댑터(vNIC)와 가상 스위치(vSwitch)</strong></li>
</ul>
<pre><code>### **가상 이더넷 어댑터(vNIC)란?**

- **정의**: 물리적 네트워크 인터페이스 카드(NIC)를 소프트웨어적으로 구현한 네트워크 장치.
- **역할**:
    - 가상 머신이 네트워크에 연결되도록 지원.
    - 물리적 NIC와 동일하게 IP 주소를 할당받고 데이터를 송수신.
    - 가상 머신은 이 vNIC를 실제 네트워크 장치처럼 사용.

### **가상 스위치(vSwitch)란?**

- **정의**: 물리적 네트워크 스위치를 소프트웨어적으로 구현한 것.
- **역할**:
    - 가상 머신 간 통신을 가능하게 함.
    - 가상 머신과 물리적 네트워크 간 트래픽을 라우팅.
    - 네트워크 패킷을 관리하고 전달.

### **vNIC와 vSwitch의 상호작용**:

1. 가상 머신이 네트워크에 데이터를 보내려 하면:
    - vNIC를 통해 데이터를 송신.
    - 가상 스위치(vSwitch)가 데이터를 수신하고, 목적지(다른 가상 머신 또는 외부 네트워크)로 전달.
2. 외부 네트워크에서 가상 머신으로 데이터를 보내려 하면:
    - 가상 스위치(vSwitch)가 해당 데이터를 수신.
    - 데이터 패킷을 가상 머신의 vNIC로 전달.</code></pre><p><strong>Self Check!</strong></p>
<p>아래의용어를설명해보세요.
<strong>• 하이퍼바이저?</strong></p>
<p>: 가상화 환경에서 물리적인 자원을 논리적으로 활용할 수 있게 관리·감독하는 역할</p>
<p>TYPE1,2가 있고 2는 운영체제에서 1은 가상머신위에서 작동한다. </p>
<p><strong>• 온프레미스?</strong> </p>
<p>: DC(데이터센터)를 외부에 의존하지 않고 모든 과정을 직접 운영하는 형태.
외부에 의존하지 않고 모든 과정을 직접 운영하는 형태&quot;라는 것은 <strong>온프레미스(On-Premises)</strong> 데이터 센터를 의미 , 이는 기업이나 조직이 자체적으로 서버, 네트워크 장비, 저장 장치를 구매하고 관리하여 데이터를 저장하고 처리하는 방식입니다.</p>
<p><strong>• 하이브리드클라우드</strong></p>
<p>: 퍼블릭클라우드 + 프라이빗클라우드 를 합한 클라우드  </p>
<ul>
<li><strong>Azure 가상화 실습</strong></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/06e5f58b-b51b-459e-85c4-39dad1736e9a/image.png" /></p>
<pre><code>**Azure구독** :  

→ Azure에서 리소스를 **프로비저닝**하는데 사용되는 논리적인 컨테이너

&quot;리소스를 프로비저닝(provisioning)한다&quot;는 IT나 클라우드 컴퓨팅에서 **필요한 리소스(자원)를 준비하고 제공하는 과정**

**구독**은 Azure에서 **서비스를 이용하는 단위**

→ 하나의 구독에는 여러 리소스(예: 가상 머신, 데이터베이스, 네트워크 등)가 포함

리소스그룹 

리소스</code></pre><ul>
<li><p><strong>보안그룹</strong></p>
<p>  <strong>네트워크보안그룹</strong>
  • Azure 리소스와 주고받는 네트워크 트래픽을 필터링</p>
</li>
</ul>
<h2 id="azure-실습">Azure 실습</h2>
<p><strong>Apache2</strong>는 <strong>Apache HTTP Server</strong>의 두 번째 주요 버전으로, 가장 널리 사용되는 <strong>웹 서버</strong> 중 하나입니다. Apache2는 웹 서버 소프트웨어로, <strong>웹 페이지</strong>를 클라이언트(브라우저)로 전달하는 역할을 합니다. 주로 <strong>Linux</strong>와 <strong>Unix</strong> 시스템에서 사용되지만, <strong>Windows</strong>에서도 실행될 수 있습니다.</p>
<ul>
<li><strong>웹브라우저에서 가상머신의 공용 IP로 접속 테스트</strong></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/9c576745-c268-4dee-b3c6-a2630a36c7ba/image.png" /></p>
<h3 id="3-tier-architecture-또는-web-server-구조--bastion-host-또는-jump-server-구조">3-Tier Architecture 또는 Web server 구조 &amp; Bastion Host&quot; 또는 &quot;Jump Server&quot; 구조</h3>
<ul>
<li><strong>vm1 =점프박스 = Bastion (요새 )Host</strong></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/c301ff16-1df1-4f76-9d88-1fd6c780b86b/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/a9b5fe62-66e1-4c86-9fdd-314aa2cd94cf/image.png" /></p>
<ul>
<li><p><strong>Azure</strong></p>
<p>  <strong>Azure 란?</strong> </p>
<p>  → <strong>마이크로소프트가 제공하는 클라우드 컴퓨팅 플랫폼 및 서비스</strong></p>
<p>  <strong>특징</strong> </p>
<p>   <strong>1. IaaS, PaaS, SaaS 지원</strong></p>
<p>   <strong>2. 글로벌 인프라 : 전세계적으로 데이터 센터가 있다.</strong>  </p>
<p>  <strong>제공서비스</strong>  </p>
<ul>
<li><p><strong>1. 컴퓨팅서비스</strong></p>
<p>  <strong>Azure Virtual Machines:</strong> 가상 서버 제공.</p>
</li>
<li><p><strong>2. 스토리지</strong></p>
<p>  <strong>Azure Blob Storage:</strong> 비정형 데이터(이미지, 동영상 등) 저장.
  <strong>Azure Disk:</strong> VM용 디스크 저장소.</p>
</li>
<li><p><strong>3. 네트워킹</strong></p>
<ul>
<li><p><strong>Azure Virtual Network (VNet):</strong> 가상 네트워크 설정.</p>
</li>
<li><p><strong>Azure CDN:</strong> 콘텐츠 배포 네트워크.</p>
<p>→ 이 두 개는 <strong>이더넷과 스위치</strong>의 역할을 가상공간에서 하고 있다고 이해 할 수 있다.</p>
</li>
<li><p><strong>이더넷 &amp; 스위치</strong></p>
<ul>
<li><strong>이더넷</strong>은 데이터를 전송하는 <strong>프로토콜(규칙)</strong>이며, <strong>스위치</strong>는 그 데이터를 목적지까지 효과적으로 전달하는 <strong>장비</strong>입니다.</li>
<li>스위치는 이더넷의 규칙을 기반으로 작동하며, 네트워크 효율성을 높이는 데 중요한 역할을 합니다.</li>
</ul>
</li>
<li><p><strong>Azure Load Balancer:</strong> 트래픽 부하 분산.</p>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/d3b76dd8-0938-432e-903b-f6013010132a/image.png" /></p>
<p><strong>Self Check!</strong>
아래의용어를설명해보세요.</p>
<p><strong>• Azure Location?</strong> </p>
<p>: Azure Location은 <strong>Microsoft Azure 데이터 센터의 물리적 지리적 위치</strong>를 나타냅니다.</p>
<p>Azure는 전 세계적으로 데이터 센터를 운영하며, 이 데이터 센터들은 특정 지역(Region)으로 그룹화됩니다.</p>
<ul>
<li><strong>특징 및 주요 정보</strong>:<ul>
<li>Azure Region은 여러 <strong>Location</strong>으로 구성됩니다.</li>
<li>예: <code>East US</code>, <code>West Europe</code>, <code>Korea Central</code> 등.</li>
<li>각 Location은 규제 요건, 데이터 거버넌스, 성능 요구 사항에 맞춰 선택할 수 있습니다.</li>
</ul>
</li>
</ul>
<h3 id="-azure-availability-zone">• Azure <strong>Availability Zone?</strong></h3>
<p>→   <strong>Availability 가용성 (원하는 시점에 사용할 준비가 되어 있는지)</strong></p>
<p>:  Azure Availability Zone은 <strong>Azure Region 내의 물리적으로 분리된 데이터 센터 그룹</strong>을 의미합니다.</p>
<ul>
<li><strong>특징</strong>:<ul>
<li><strong>고가용성</strong>(High Availability)을 보장하기 위해 설계.</li>
<li>동일한 Region 내에서 논리적으로 연결되면서도 <strong>격리된 위치</strong>.</li>
<li>Zone은 독립적인 전원, 냉각, 네트워크를 제공합니다.</li>
<li><strong>실제 사용 예</strong>:<ul>
<li>주요 응용 프로그램을 여러 Zone에 배치하여 장애 복구(Failover)와 가용성을 높임.</li>
</ul>
</li>
</ul>
</li>
</ul>
<h3 id="-azure-disk">• Azure <strong>Disk</strong>?</h3>
<p>:  Azure Disk는  <strong>Azure VM의 클라우드 기반 스토리지.</strong></p>
<ul>
<li><strong>인바운드 연결</strong> , 외부에서 내부로 들어오는 <strong>네트워크 요청</strong></li>
<li><strong>아웃바운드 연결</strong>은 쉽게 말하면, <strong>내부에서 외부로 나가는 네트워크 요</strong></li>
</ul>
<h2 id="load-balancer"><strong>Load Balancer</strong></h2>
<p>외부에서 트레픽이 많아질때 서버 부하가 걸린다</p>
<p>이때 로드밸런서 <strong>Load Balancer ( 부하 분산 장치 )</strong> 를 사용해서 다수의 서버로 분산시킨다. </p>
<p> OSI 모델의 L4 에서 작동</p>
<h2 id="오토스케일링">오토스케일링</h2>
<p>트래픽이 많아지면 알아서 vm을 만들어준다. </p>
<h3 id="vmss와-vmss-인스턴스의-차이"><strong>VMSS와 VMSS 인스턴스의 차이</strong></h3>
<table>
<thead>
<tr>
<th><strong>항목</strong></th>
<th><strong>VMSS</strong></th>
<th><strong>VMSS 인스턴스</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>정의</strong></td>
<td>VMSS는 VM의 그룹을 관리하는 서비스</td>
<td>VMSS가 생성한 개별 가상 머신</td>
</tr>
<tr>
<td><strong>역할</strong></td>
<td>인스턴스를 생성, 관리, 확장, 축소</td>
<td>실제로 워크로드를 처리하는 단위</td>
</tr>
<tr>
<td><strong>특징</strong></td>
<td>- 중앙에서 관리- 자동 스케일링, 부하 분산 지원</td>
<td>- 독립된 VM으로 동작- 사용자 요청 처리</td>
</tr>
<tr>
<td><strong>관리</strong></td>
<td>정책, 템플릿, 스케일 규칙 설정 등</td>
<td>VM 인스턴스는 VMSS에 의해 자동 관리</td>
</tr>
<tr>
<td><strong>예시</strong></td>
<td>- 스케일셋의 크기 조정- VM 배포, 삭제 관리</td>
<td>- VM01, VM02 같은 개별 가상 머신</td>
</tr>
</tbody></table>
<ul>
<li>즉, <strong>VMSS</strong>(Virtual Machine Scale Sets)는 동일한 구성을 가진 여러 가상 머신(VM)을 자동으로 생성하고 관리할 수 있는 Azure의 서비스이고, <strong>VMSS 인스턴스</strong>는 이 VMSS에 의해 생성된 개별 가상 머신을 의미합니다. 쉽게 말해, <strong>VMSS는 인스턴스들을 묶어서 관리하는 그룹</strong>이고, <strong>VMSS 인스턴스는 해당 그룹 내의 개별 VM</strong>입니다.</li>
</ul>
<h3 id="horizontal-vs-vertical-scaling"><strong>Horizontal vs Vertical Scaling</strong></h3>
<table>
<thead>
<tr>
<th><strong>항목</strong></th>
<th><strong>Horizontal Scaling</strong></th>
<th><strong>Vertical Scaling</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>확장 방식</strong></td>
<td>여러 시스템 추가</td>
<td>기존 시스템 업그레이드</td>
</tr>
<tr>
<td><strong>설정 복잡성</strong></td>
<td>복잡함 (분산 시스템, 데이터 동기화)</td>
<td>간단함 (기존 시스템만 업그레이드)</td>
</tr>
<tr>
<td><strong>확장 한계</strong></td>
<td>무제한 (이론적으로 가능)</td>
<td>물리적 한계 존재</td>
</tr>
<tr>
<td><strong>비용</strong></td>
<td>초기 비용 낮음, 운영 중 비용 효율적</td>
<td>초기 비용 높음</td>
</tr>
<tr>
<td><strong>단일 장애점</strong></td>
<td>제거 가능 (노드 추가로 대체)</td>
<td>단일 장애점 존재</td>
</tr>
<tr>
<td>- 두 방법 모두 시스템 확장성을 개선하지만, 현대의 클라우드 기반 환경에서는 <strong>Horizontal Scaling</strong>이 더 많이 사용됩니다. 이는 분산 시스템과 클라우드 서비스가 이를 지원하도록 설계되었기 때문입니다.</td>
<td></td>
<td></td>
</tr>
</tbody></table>
<h2 id="docker">Docker</h2>
<p><strong>도커(Docker)</strong>는 애플리케이션과 필요한 모든 구성 요소를 하나의 패키지로 묶어 배포할 수 있는 <strong>컨테이너화 플랫폼</strong>입니다. 이를 통해 애플리케이션을 어느 환경에서든 일관되게 실행할 수 있도록 도와줍니다.</p>
<h3 id="도커"><strong>도커</strong></h3>
<ol>
<li><p><strong>컨테이너(Container)</strong>:</p>
<ul>
<li>애플리케이션과 그 실행에 필요한 라이브러리, 종속성, 설정 파일 등을 독립적으로 실행할 수 있는 경량화된 가상 환경.</li>
<li>같은 호스트 OS를 공유하면서도 각 애플리케이션이 서로 독립적으로 실행됩니다.</li>
<li>컨테이너는 <strong>가상 머신(VM)</strong>보다 가볍고 빠르게 시작할 수 있음.</li>
</ul>
</li>
<li><p><strong>이미지(Image)</strong>:</p>
<ul>
<li><strong>컨테이너를 실행하기 위한 템플릿.</strong></li>
<li>애플리케이션과 모든 종속성을 포함하며, 변경되지 않는 읽기 전용 파일 시스템.</li>
<li><strong>컨테이너는 이 이미지를 기반으로 생성</strong>됩니다.</li>
</ul>
</li>
<li><p><strong>도커 엔진(Docker Engine)</strong>:</p>
<ul>
<li>도커의 핵심 소프트웨어로, 컨테이너를 생성하고 실행하는 역할.</li>
<li><strong>도커 클라이언트</strong>와 <strong>도커 데몬</strong>으로 구성.</li>
</ul>
</li>
<li><p><strong>도커 허브(Docker Hub)</strong>:</p>
<ul>
<li><strong>도커 이미지를 저장하고 공유할 수 있는 클라우드 기반 레지스트리.</strong></li>
<li>공식 이미지와 커뮤니티가 만든 이미지를 다운로드 가능.</li>
</ul>
</li>
</ol>
<h3 id="도커와-가상-머신vm의-차이"><strong>도커와 가상 머신(VM)의 차이</strong></h3>
<table>
<thead>
<tr>
<th><strong>항목</strong></th>
<th><strong>도커 컨테이너</strong></th>
<th><strong>가상 머신(VM)</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>구조</strong></td>
<td>호스트 OS의 커널 공유</td>
<td>하드웨어에 독립적인 OS 실행</td>
</tr>
<tr>
<td><strong>부팅 시간</strong></td>
<td>몇 초 이내</td>
<td>수 분 소요</td>
</tr>
<tr>
<td><strong>성능</strong></td>
<td>경량, 빠름</td>
<td>상대적으로 무거움</td>
</tr>
<tr>
<td><strong>리소스 사용</strong></td>
<td>효율적</td>
<td>더 많은 리소스 사용</td>
</tr>
<tr>
<td><strong>이식성</strong></td>
<td>뛰어남</td>
<td>제한적</td>
</tr>
</tbody></table>
<h3 id="왜-의존성-설치가-필요한가"><strong>왜 의존성 설치가 필요한가?</strong></h3>
<ul>
<li><strong>Docker는 운영 체제에 따라 별도의 저장소를 사용</strong>하며, 이를 통해 안정적이고 최신 버전의 소프트웨어를 제공합니다. <strong>의존성 설치는 이러한 저장소와의 연결 및 보안을 설정하기 위한 준비 작업</strong>입니다.</li>
</ul>
<h3 id="nginx란"><strong>Nginx란?</strong></h3>
<p><strong>Nginx</strong>는 웹 서버 소프트웨어로, HTTP 서버 역할을 수행하며 다음과 같은 특징을 같다.</p>
<h3 id="8080-포트"><strong>8080 포트</strong></h3>
<p><strong>8080 포트</strong>: HTTP 트래픽을 처리하기 위해 사용되며, 테스트 및 개발용으로 적합.</p>
<ul>
<li><strong>Docker</strong>는 애플리케이션을 <strong>컨테이너화</strong>하여 이동성과 일관성을 제공하는 툴입니다.</li>
<li><strong>Azure</strong>는 <strong>클라우드 인프라</strong>를 제공하며, Docker와 같은 컨테이너화된 애플리케이션을 <strong>확장성 있고 관리 가능한</strong> 환경에서 실행할 수 있게 도와줍니다.</li>
<li><strong>두 서비스를 함께 사용</strong>함으로써, <strong>애플리케이션의 효율적인 배포, 관리, 확장</strong>이 가능해지고, <strong>클라우드 환경에서 데이터와 자원을 통합적으로 관리</strong>할 수 있습니다.</li>
</ul>
<p>이렇게 Docker와 Azure는 서로 보완적인 역할을 하여 <strong>컨테이너화된 애플리케이션을 클라우드에서 효율적으로 실행</strong>하고 관리하는 데 매우 유용합니다.</p>
<ul>
<li><strong>애플리케이션</strong>은 특정 작업을 수행하는 프로그램이고,</li>
<li><strong>컨테이너화된 애플리케이션</strong>은 애플리케이션을 <strong>독립적이고 이동 가능한</strong> 환경(컨테이너)으로 포장한 것입니다. 이를 통해 <strong>다양한 환경에서 일관되게 애플리케이션을 실행</strong>할 수 있습니다.</li>
</ul>
<h3 id="→-비유를-통한-이해"><strong>→ 비유를 통한 이해</strong>:</h3>
<ol>
<li><strong>애플리케이션</strong>: 한 사람의 요리입니다. 각 요리는 특정 재료와 조리법에 따라 만들어집니다.</li>
<li><strong>컨테이너화</strong>: 요리를 만들 때 필요한 모든 재료와 도구를 <strong>하나의 통</strong>에 담아 이동하거나 보관하는 것입니다. 이 통은 다른 환경에서도 동일한 요리를 만들 수 있게 합니다.</li>
<li><strong>컨테이너화된 애플리케이션</strong>: 요리 통을 사용하여, 원하는 장소(집, 호텔, 레스토랑 등)에서 똑같은 요리를 할 수 있게 된 것입니다. 환경이나 장소에 상관없이 항상 동일한 요리를 만들 수 있습니다.</li>
</ol>
<h3 id="1-container-image"><strong>1. Container Image</strong></h3>
<ul>
<li><em>컨테이너 이미지(Container Image)*</em>는 <strong>컨테이너를 실행하기 위한 템플릿</strong>입니다.</li>
<li>애플리케이션과 실행에 필요한 모든 파일(코드, 라이브러리, 설정 등)을 포함한 <strong>읽기 전용 패키지</strong>입니다.</li>
<li><strong>컨테이너</strong>는 <strong>컨테이너 이미지</strong>를 기반으로 생성됩니다.</li>
<li>이미지는 불변(immutable)하며, 여러 환경에서 동일하게 사용할 수 있습니다.</li>
<li>쉽게 말해, <strong>컨테이너를 실행하기 위한 설계도</strong>라고 볼 수 있습니다.</li>
</ul>
<p><strong>비유</strong>: 레스토랑 요리사의 표준 레시피. (컨테이너 = 레시피로 만든 요리)</p>
<hr />
<h3 id="2-dockerfile"><strong>2. Dockerfile</strong></h3>
<p><strong>Dockerfile</strong>은 <strong>컨테이너 이미지를 생성하기 위한 스크립트 파일</strong>입니다.</p>
<ul>
<li>이미지 빌드 과정에서 사용되는 <strong>명령어들의 리스트</strong>가 포함되어 있습니다.</li>
<li>Dockerfile을 사용하면 반복 가능한 방식으로 이미지를 만들 수 있습니다.</li>
</ul>
<h3 id="구조"><strong>구조</strong>:</h3>
<p>Dockerfile에는 아래와 같은 내용이 포함됩니다:</p>
<ul>
<li><strong>기반 이미지 선택</strong>: <code>FROM</code> 명령어를 사용해 기반이 되는 이미지를 정의.</li>
<li><strong>추가 작업 정의</strong>: 애플리케이션 복사, 라이브러리 설치, 명령 실행 등.</li>
<li><strong>최종 실행 명령</strong>: 컨테이너 실행 시 수행할 작업 지정.</li>
</ul>
<hr />
<h3 id="3-docker-hub"><strong>3. Docker Hub</strong></h3>
<p><strong>Docker Hub</strong>는 <strong>Docker 이미지를 저장하고 공유할 수 있는 클라우드 기반의 레지스트리</strong>입니다.</p>
<ul>
<li>개발자는 자신의 이미지를 Docker Hub에 업로드하여 공유할 수 있습니다.</li>
<li>이미 만들어진 <strong>공식 이미지</strong>나 <strong>커뮤니티가 만든 이미지</strong>를 다운로드해 사용할 수 있습니다.</li>
<li>Docker Hub를 통해 여러 프로젝트에서 <strong>이미지를 관리, 배포</strong>할 수 있습니다.</li>
</ul>
<h3 id="사용-예"><strong>사용 예</strong>:</h3>
<ul>
<li><code>docker pull nginx</code> 명령어로 Docker Hub에서 Nginx 이미지를 다운로드.</li>
<li>개인 프로젝트의 이미지를 <code>docker push</code> 명령으로 Docker Hub에 업로드.</li>
</ul>
<p><strong>비유</strong>: Docker 이미지를 보관하고 공유할 수 있는 <strong>온라인 이미지 창고</strong>.</p>
<h3 id="요약"><strong>요약</strong></h3>
<ul>
<li><strong>Container Image</strong>: 컨테이너 실행을 위한 템플릿 (불변).</li>
<li><strong>Dockerfile</strong>: 이미지를 생성하기 위한 스크립트 파일 (설계도).</li>
<li><strong>Docker Hub</strong>: Docker 이미지를 저장하고 공유할 수 있는 클라우드 플랫폼.</li>
</ul>
<p>Docker와 Kubernetes는 <strong>소프트웨어 기능(애플리케이션)</strong>을 더 효율적이고 안정적으로 배포, 실행, 관리하기 위한 도구입니다. 둘 다 목적은 비슷하지만, <strong>사용 범위와 역할</strong>이 다릅니다.</p>
<hr />
<ol>
<li><p><strong>Docker는 컨테이너를 생성</strong>하고 실행하는 역할을 합니다.</p>
</li>
<li><p><strong>Kubernetes는 Docker를 포함한 컨테이너를 관리</strong>합니다.</p>
<ul>
<li>Kubernetes는 Docker뿐만 아니라 containerd, CRI-O 같은 다양한 컨테이너 런타임도 지원.</li>
</ul>
</li>
<li><p><strong>Container : VM을 가상화시켜 공간을 만듦</strong> </p>
</li>
<li><p><strong>Docker : Container를 만들고 관리해주는 프로그램</strong> </p>
</li>
<li><p><strong>Kubernetes : 컨테이너 오케스트레이션 도구 = 여러서버에서 실행중인 도커를 관리</strong></p>
</li>
</ol>
<ul>
<li><strong>컨테이너</strong>: 애플리케이션 실행을 위한 독립적 환경.</li>
<li><strong>클러스터</strong>: 다수의 컨테이너를 실행하고 관리하기 위한 환경.</li>
<li><strong>네임스페이스</strong>: 클러스터 내부의 리소스를 논리적으로 구분.</li>
<li><strong>Pod</strong>: Kubernetes에서 컨테이너를 실행하는 최소 단위.</li>
<li><strong>Bastion Host</strong>: 보안을 강화하기 위한 네트워크 접근 게이트웨이.</li>
<li><strong>Docker vs Kubernetes</strong>: Docker는 개별 컨테이너 실행, Kubernetes는 전체 관리.</li>
</ul>
<h3 id="1-deployment"><strong>1. Deployment</strong></h3>
<p><strong>Deployment</strong>는 Kubernetes에서 애플리케이션을 실행하고 관리하는 데 필요한 &quot;객체&quot;들 = 구성 요소</p>
<h3 id="2-pod"><strong>2. Pod</strong></h3>
<p>Kubernetes에서 <strong>Pod</strong>는 컨테이너를 실행하는 <strong>최소 단위(하나 이상 컨테이너가능-</strong> 이  컨테이너들은 <strong>같은 네트워크 환경</strong>에서 실행되며, <strong>자원을 공유가능)</strong></p>
<ul>
<li>예를 들어, Nginx 웹 서버는 하나의 컨테이너로 실행될 수 있습니다. 이 컨테이너를 실행하는 것이 바로 <strong>Pod</strong>입니다. 하나의 Pod는 Nginx와 같은 애플리케이션을 포함하고 있으며, Kubernetes는 이 Pod를 <strong>스케줄링하고 관리</strong>합니다.</li>
</ul>
<p><strong>즉, Pod는 컨테이너를 실행하는 집합체</strong>입니다. Nginx를 실행하려면 <strong>Pod</strong>가 필요하고, Deployment는 여러 Pod를 생성하거나 관리할 수 있도록 합니다.</p>
<h3 id="3-replicas란">3. replicas란</h3>
<p><strong>replicas</strong>는 Kubernetes에서 Deployment를 통해 실행될 <strong>Pod의 복제본 수</strong>를 지정하는 설정</p>
<h3 id="1-kubernetes-리소스--건물-관리-시스템"><strong>1. Kubernetes 리소스 = 건물 관리 시스템</strong></h3>
<p>Kubernetes는 마치 <strong>건물 관리 시스템</strong>과 같다고 볼 수 있습니다. 이 시스템은 건물(클러스터)을 관리하고, 각 방(리소스)들을 어떻게 사용할지, 배치할지를 결정합니다.</p>
<ul>
<li><strong>Kubernetes 클러스터 = 건물</strong>Kubernetes 클러스터는 <strong>건물</strong>입니다. 이 건물 안에는 다양한 <strong>방</strong>들이 있고, 각각의 방에서는 <strong>특정 작업이나 서비스</strong>가 진행됩니다.</li>
</ul>
<h3 id="2-pod--방"><strong>2. Pod = 방</strong></h3>
<ul>
<li><p><strong>Pod = 방</strong></p>
<p>  <strong>Pod</strong>는 Kubernetes에서 <strong>컨테이너를 실행하는 최소 단위</strong>입니다. 이 Pod는 <strong>하나 이상의 컨테이너</strong>를 실행할 수 있는 <strong>방</strong>과 같습니다. 예를 들어, 한 방(Pod)에서 <strong>웹 서버</strong>와 <strong>로그 수집기</strong>가 함께 실행될 수 있습니다.</p>
<ul>
<li><strong>Pod 안에 여러 개의 컨테이너</strong>가 있을 수 있으며, 그 방에서는 동일한 네트워크를 사용하고 자원을 공유합니다.</li>
</ul>
</li>
</ul>
<h3 id="3-deployment--건물의-관리팀"><strong>3. Deployment = 건물의 관리팀</strong></h3>
<ul>
<li><p><strong>Deployment = 건물의 관리팀</strong></p>
<p>  <strong>Deployment</strong>는 마치 <strong>건물 관리팀</strong>처럼, 여러 개의 방(Pod)을 관리하고 조정합니다. 예를 들어, 관리팀은 방을 여러 개 만들어야 한다면 몇 개를 만들지, 방을 교체해야 한다면 어떻게 해야 할지 결정합니다.</p>
<ul>
<li><strong>Pod의 복제본을 관리</strong>하고, <strong>업데이트</strong>를 처리하는 일을 합니다. 예를 들어, &quot;Nginx 웹 서버가 실행될 방 3개를 만들어줘&quot;라고 요청할 때, Deployment가 그 작업을 합니다</li>
</ul>
</li>
</ul>
<h3 id="4-replicas--방의-개수"><strong>4. replicas = 방의 개수</strong></h3>
<ul>
<li><p><strong>replicas = 방의 개수</strong></p>
<p>  <strong>replicas</strong>는 &quot;몇 개의 방(Pod)을 만들 것인가?&quot;를 결정하는 수입니다. 예를 들어, &quot;웹 서버를 실행할 방을 3개 만들겠다&quot;라고 설정하는 것이 바로 <strong>replicas</strong>입니다.</p>
<ul>
<li>3개의 Pod(방)를 실행하여 웹 서버를 제공하려면, Deployment는 이를 관리하고 실행합니다.</li>
</ul>
</li>
</ul>
<h3 id="5-service--건물-입구-외부와-연결하는-통로"><strong>5. Service = 건물 입구 (외부와 연결하는 통로)</strong></h3>
<ul>
<li><p><strong>Service = 건물 입구</strong></p>
<p>  Service를 통해 <strong>외부 트래픽을 클러스터 내의 Pod들로 라우팅</strong></p>
<ul>
<li>예를 들어, 서비스가 &quot;웹 서버가 있는 방(Pod)으로 들어오는 트래픽을 처리해줘&quot;라고 요청합니다. Service는 외부에서 들어오는 요청을 Pod에 자동으로 전달합니다.</li>
</ul>
</li>
</ul>
<h3 id="6-namespace--건물의-층"><strong>6. Namespace = 건물의 층</strong></h3>
<ul>
<li><p><strong>Namespace = 건물의 층</strong></p>
<p>  <strong>Namespace</strong>는 Kubernetes 클러스터 내에서 리소스를 논리적으로 <strong>분리</strong>하고 관리할 수 있는 방법입니다. 예를 들어, 큰 건물에서 여러 층을 나누어 관리하는 것처럼, 각 층에 특정한 작업이나 서비스를 할당할 수 있습니다.</p>
<ul>
<li>예를 들어, <code>dev</code>(개발) 환경과 <code>prod</code>(운영) 환경을 <strong>별도의 층</strong>으로 분리하여 관리할 수 있습니다.</li>
</ul>
</li>
</ul>
<h3 id="7-ingress--건물-내의-안내판"><strong>7. Ingress = 건물 내의 안내판</strong></h3>
<ul>
<li><p><strong>Ingress = 건물 내의 안내판</strong></p>
<p>  <strong>Ingress</strong>는 클러스터 외부에서 들어오는 HTTP(S) 요청을 <strong>건물 내의 특정 층으로 안내하는 역할</strong>을 합니다. 예를 들어, 웹사이트를 운영하는 경우, 특정 URL 경로에 따라 요청을 다른 Pod(방)으로 라우팅할 수 있습니다.</p>
<ul>
<li>예를 들어, <code>example.com/api</code>로 들어오는 트래픽을 <code>api-service</code>로, <code>example.com/web</code>로 들어오는 트래픽을 <code>web-service</code>로 보내는 역할을 합니다.</li>
</ul>
</li>
</ul>
<h3 id="8-persistentvolume-pv--persistentvolumeclaim-pvc--저장-공간"><strong>8. PersistentVolume (PV) &amp; PersistentVolumeClaim (PVC) = 저장 공간</strong></h3>
<ul>
<li><strong>PersistentVolume (PV) = 저장소</strong><ul>
<li><em>PersistentVolume (PV)*</em>는 <strong>건물 내의 저장 공간</strong>과 같으며, 이 공간은 물리적인 저장소에 대응합니다. 예를 들어, 특정 방(Pod)에서 데이터베이스를 운영하려면 데이터를 <strong>영구적으로 저장할 수 있는 공간</strong>이 필요합니다.</li>
</ul>
</li>
<li><strong>PersistentVolumeClaim (PVC) = 저장소 요청</strong><ul>
<li><em>PersistentVolumeClaim (PVC)*</em>는 <strong>저장 공간에 대한 요청</strong>입니다. 예를 들어, &quot;나는 100GB 크기의 저장 공간이 필요하다&quot;라고 요청하는 것이 PVC입니다.</li>
<li>PVC가 요청하면, Kubernetes는 적절한 <strong>PersistentVolume(PV)</strong>을 할당해 주어, Pod에서 데이터를 영구적으로 저장할 수 있게 합니다.</li>
</ul>
</li>
</ul>
<h3 id="nodeport와-다른-service-유형-비교"><strong>NodePort와 다른 Service 유형 비교</strong></h3>
<table>
<thead>
<tr>
<th><strong>Service 유형</strong></th>
<th><strong>설명</strong></th>
<th><strong>사용 사례</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>ClusterIP</strong></td>
<td>클러스터 내부에서만 접근 가능.</td>
<td>Pod 간 내부 통신.</td>
</tr>
<tr>
<td><strong>NodePort</strong></td>
<td>클러스터 외부에서 노드 IP와 포트를 통해 접근 가능.</td>
<td>간단한 외부 접근.</td>
</tr>
<tr>
<td><strong>LoadBalancer</strong></td>
<td>클라우드 환경에서 외부 로드 밸런서를 통해 접근 가능.</td>
<td>외부에서의 고가용성 접근.</td>
</tr>
<tr>
<td><strong>ExternalName</strong></td>
<td>외부 DNS 이름을 클러스터 내부 서비스 이름으로 매핑.</td>
<td>외부 리소스를 내부처럼 사용.</td>
</tr>
</tbody></table>
<p><strong>Worker1 로의 접근을 통해 통신 확인
→ curl &lt;Worker 1 노드의 IP&gt;:30000</strong></p>
<ul>
<li><code>curl</code> 명령에서 <strong>외부 IP</strong>를 사용해야 하는 이유는 외부 네트워크에서 요청을 보내기 때문이다.</li>
<li>예를 들어, <code>curl &lt;외부 IP&gt;:30000</code>로 접근하면 해당 노드에서 <code>NodePort</code>로 노출된 서비스에 접근할 수 있다.</li>
</ul>
<p><strong>멀티클라우드</strong>는 여러 클라우드 서비스 제공자(CSP)의 서비스를 동시에 사용하는 방식을 의미. 하나의 CSP에 종속되지 않고 다양한 클라우드의 장점을 활용하여 시스템의 유연성과 확장성을 높이고, 리스크를 분산시키는 것이 목적이다.</p>
<p><strong>가상머신</strong>은 사용이 끝나면 VM 자체가 삭제되지만, 연결된 <strong>스토리지는 삭제되지 않고</strong> 그대로 남고 VM과 연결된 스토리지는 별도로 관리할 수 있다.</p>
<p>기본적으로 <strong>Namespace를 지정하지 않으면 <code>default</code> namespace</strong>에 리소스가 생성되며 <code>kube-system</code>은 Kubernetes 시스템 리소스가 위치하는 특별한 네임스페이스이며, 자동으로 선택되지 않는다. 따라서 &quot;kube-system&quot;에 리소스가 자동으로 생성된다는 설명은 틀린 내용이다.</p>
<p>상태 프로브는 백엔드 인스턴스의 건강 상태를 모니터링하는 역할</p>