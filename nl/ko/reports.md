---

copyright:
  years: 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# 유형별 보고서 세부사항

## 방화벽 로그인
{: #firewalllogins}

Vyatta 방화벽 디바이스에 대한 관리자 로그인과 관련된 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>이벤트 이름</dt>
<dd>이벤트의 유형입니다(사용자가 SSH를 통해 로그인하는 데 실패함 - 올바르지 않은 비밀번호, 인증 실패, 세션 닫힘, 사용자에 대해 비밀번호 수락됨, 사용자에 대해 세션 열림). </dd>
<dt>하위 레벨 카테고리</dt>
<dd>이벤트 세부사항입니다(SSH 로그인 실패, 세션 닫힘, 호스트 로그인 성공, 세션 열림). </dd>
<dt>사용자 이름</dt> 
<dd>세션을 시작한 사용자의 신임 정보(사용자 이름)입니다. </dd>
<dt>소스 IP</dt>
<dd>사용자가 세션을 시작한 IP 주소입니다.
<dt>대상 IP</dt>
<dd>세션의 대상입니다. </dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 방화벽의 호스트 이름). </dd>
</dl>

## 방화벽 거부
{: #firewalldenies}

적용 중인 방화벽 규칙에 의해 액세스 요청이 거부되는 경우 Vyatta 방화벽 디바이스가 생성하는 이벤트를 보고합니다. 
  
### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜 및 시간입니다. </dd>
<dt>이벤트 이름</dt>
<dd>이벤트의 유형입니다(사용자가 SSH를 통해 로그인하는 데 실패함 - 올바르지 않은 비밀번호, 인증 실패, 세션 닫힘, 사용자에 대해 비밀번호 수락됨, 사용자에 대해 세션 열림). </dd>
<dt>하위 레벨 카테고리</dt>
<dd>방화벽 거부 이벤트의 세부사항입니다. </dd>
<dt>소스 IP</dt> 
<dd>네트워크 연결 및/또는 공격이 시작된 소스 IP 주소입니다. </dd>
<dt>소스 포트</dt>
<dd>프로토콜 대상 포트입니다.
<dt>대상 IP</dt>
<dd>세션의 대상입니다. </dd>
<dt>대상 포트</dt>
<dd>프로토콜 대상 포트입니다. </dd>
<dt>프로토콜</dt>
<dd>통신 프로토콜입니다(tcp/udp).
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 방화벽의 호스트 이름). </dd>
<dt>이벤트 개수</dt>
<dd>해당 유형의 이벤트 수입니다. </dd>
</dl>

## 운영 체제 로그인
{: #oslogin}

관리자가 Bluemix 시스템에서 SSH 세션을 시작할 때 운영 체제가 생성하는 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>이벤트 이름</dt>
<dd>이벤트의 유형입니다(사용자 영역 인증, 사용자 영역 인증 실패). </dd>
<dt>사용자 이름</dt> 
<dd>인증 프로세스를 시작한 사용자의 사용자 이름입니다. </dd>
<dt>소스 주소</dt>
<dd>사용자가 세션을 시작한 IP 주소입니다.
<dt>대상 IP</dt>
<dd>세션의 대상입니다. </dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트가 생성된 서버의 호스트 이름). </dd>
</dl>

## 로그인 서버 로그인 
{: #loginserverlogins}

Bluemix 플랫폼 사용자가 명령행, REST API 또는 Bluemix 콘솔을 사용하여 세션을 시작할 때 Bluemix 플랫폼 로그인 컴포넌트에서 생성하는 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>이벤트 이름</dt>
<dd>이벤트의 유형입니다(사용자 영역 인증, 사용자 영역 인증 실패). </dd>
<dt>사용자</dt> 
<dd>인증 프로세스를 시작한 사용자의 사용자 ID입니다. </dd>
<dt>Bluemix_Platform_Component</dt>
<dd>이벤트를 생성한 컴포넌트입니다(login_server).
<dt>메시지 유형</dt>
<dd>오퍼레이션의 유형입니다(로그인, 로그아웃). </dd>
<dt>상태</dt>
<dd>오퍼레이션의 결과입니다(성공/실패). </dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다. </dd>
</dl>

## 데이터베이스 관리
{: #dbadmin}

Bluemix 내부 데이터베이스에서 데이터베이스 관리자가 수행하는 오퍼레이션과 관련된 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Type</dt>
<dd>이벤트의 유형입니다(SECURITY_RUNTIME).
<dt>사용자</dt> 
<dd>오퍼레이션을 수행한 사용자의 사용자 이름입니다. 다음 사용자는 데이터베이스에 정의된 사용자입니다.
<ul>
<li>UAADB: vcap, root, backup_user.
</li>
<li>CCDB: vcap, ccadmin, backup_user.
</li>
<li>위 항목에서 벗어난 사용의 경우에는 오퍼레이션 수행자에 대한 조사가 필요합니다. 이는 운영 체제 관리 보안 보고서 및 운영 체제 로그인 보안 보고서를 사용하여 수행됩니다.
</li>
</ul>
</dd>
<dt>소스</dt> 
<dd>사용자가 명령을 시작한 IP 주소입니다. 예상 값은 다음과 같습니다.
<ul>
<li>UAADB – uaa VM 및 nfs_WAL_server VM.
</li>
<li>CCDB – api_worker, clock_global, cloud_controller_ng 및 nsf_WAL_server VM.
</li>
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>오퍼레이션의 유형입니다(CREATE, ALTER, DROP문과 같은 모든 데이터 정의 명령문 및 INSERT, UPDATE, DELETE, TRUNCATE, COPY FROM문과 같은 데이터 수정 명령문)</dd>
<dt>DB_Name</dt>
<dd>오퍼레이션이 수행된 DB 이름입니다. </dd>
</dl>

## 관리 콘솔 사용자 관리
{: #acusermgmt}

Bluemix 관리 콘솔에서 수행된 사용자 관리 활동을 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Type</dt>
<dd>이벤트의 유형입니다(SECURITY_RUNTIME).
<ul>
<li>SECURITY_MGMT_REGISTRY: Add User [user ID] </li>
<li>SECURITY_MGMT_REGISTRY: Delete User [user ID] </li>
<li>SECURITY_AUTHN_CREDS_MODIFY: Add permission [permissions] to users [user ID] </li>
<li>SECURITY_AUTHN_CREDS_MODIFY: Remove permission [permissions] from users [user ID] </li>
<li>SECURITY_MGMT_CONFIG: Create organization [name] </li>
<li>SECURITY_MGMT_CONFIG: Change organization managers [ids] </li>
<li>SECURITY_MGMT_CONFIG: Rename organization id [id] to new name [name] </li>
<li>SECURITY_MGMT_CONFIG: Delete organization id [id] </li>
<li>SECURITY_MGMT_CONFIG: Update quota for organization [id] to quota [quotaPlan]</li>
</ul>
</dd>
<dt>사용자</dt> 
<dd>오퍼레이션을 시작한 사용자입니다(LDAP ID).
<dt>메시지</dt> 
<dd>실행된 명령입니다.
<ul>
<li>Add User [user ID]: Adds 지정된 ID의 사용자를 추가합니다.</li>
<li>Delete User [user ID]: Deletes 지정된 ID의 사용자를 삭제합니다.</li>
<li>Add permission [permissions] to users [user ID]: Adds 지정된 사용자에게 권한을 추가합니다. 다음과 같은 권한이 포함될 수 있음:
ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read, ops.user.write.</li>
<li>Remove permission [permissions] from users [user ID]: Remove 권한 제거 - 지정된 사용자에서 권한을 제거합니다. 다음과 같은 권한이 포함될 수 있음: ops.admin, ops.login, ops.reports.read, ops.reports.write, ops.catalog.read, ops.catalog.write, ops.users.read, ops.users.write.</li>
<li>Create organization [name]: Creates 지정된 이름으로 조직을 작성합니다.</li>
<li>Change organization managers [ids]: Configures 조직의 관리자가 지정된 사용자가 되도록 구성합니다.</li>
<li>Rename organization id [id] to new name [name]: Renames 지정된 조직의 이름을 바꿉니다.</li>
<li>Delete User [user ID]: Deletes 지정된 ID의 사용자를 삭제합니다.</li>
<li>Delete organization id [id]: Deletes 지정된 조직을 삭제합니다.</li>
<li>Update quota for organization [id] to quota [quotaPlan]: Updates 지정된 조직의 할당량 플랜을 업데이트합니다. 다음과 같은 플랜이 포함될 수 있음: q2GB, q4GB, q8GB, q16GB, q32GB, q64GB, q128GB, q256GB, q512GB.</li>
</ul>
</dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 서버의 IP 주소/호스트 이름). </dd>
</dl>

## 카탈로그 관리
{: #catalogmgmt}

Bluemix 관리 콘솔에서 수행된 서비스 카탈로그 관리 활동과 관련된 이벤트를 보고합니다.  

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>Register template [id]. 모든 사용자의 카탈로그에 옵션으로 표시되도록 지정된 ID의 표준 유형 또는 런타임을 사용으로 설정합니다. </dd>
<dd>Deregister template [id]. 특정 표준 유형 또는 런타임이 모든 사용자의 카탈로그에 더 이상 옵션으로 표시되지 않도록 설정합니다. </dd>
<dd>Update Service Plan [id] to public = [ public ] with visibilities = [ ids ]. 지정된 서비스 플랜의 가시성을 업데이트합니다. public이 true로 설정된 경우에는 해당 플랜이 모든 조직에게 표시됩니다. public이 false로 설정된 경우에는 이 서비스 플랜이 표시되는 조직을 나타내기 위해 조직 ID 집합이 제공될 수 있습니다. </dd>
<dd>Add Service Broker [name]. 지정된 이름의 서비스 브로커를 추가합니다. </dd>
<dd>Delete Service Broker [name]. 지정된 이름의 서비스 브로커를 삭제합니다. </dd>
<dd>Update buildpack [id]. 지정된 ID의 빌드팩에 대해 빌드팩 순서 지정을 업데이트합니다. </dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 서버의 IP 주소/호스트 이름). </dd>
</dl>

## 보안 보고서 관리
{: #securityreportsmgmt}

관리 콘솔에서 수행된 보안 보고서 관리 활동과 관련된 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dd>이벤트의 유형입니다(SECURITY_RUNTIME).
<ul>
<li>SECURITY_DATA_SYNC: Upload report [name] to category [name] date [date].
Delete Report with ID [id] </li>
<li>SECURITY_RESOURCE_ACCESS: Download Report [name]. </li>
</ul>
</dd>
<dt>사용자</dt> 
<dd>오퍼레이션을 시작한 사용자입니다.
<dt>메시지</dt> 
<dd>실행된 명령입니다.
<ul>
<li>Upload report [name] to category [name] date [date]: Upload - 지정된 카테고리에 지정된 파일 이름과 날짜의 보고서를 업로드합니다.</li>
<li>Delete Report with ID [id]: Delete - 지정된 ID의 보고서를 삭제합니다.</li>
<li>Download Report [name]: Download - 지정된 이름으로 보고서가 다운로드되었습니다.</li>
</ul>
</dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 서버의 IP 주소/호스트 이름). </dd>
</dl>

## 액세스 검토
{: #accessreviews}

Bluemix 환경의 액세스 권한에 대한 요청, 그리고 이러한 요청에 대한 Bluemix 관리자의 처리를 보고합니다.  

### 데이터 필드

<dl>
<dt>Action_Name</dt>
<dd>그룹에 추가, 사용자 ID 이름 바꾸기, 취소, 그룹에서 제거 등과 같은 사용자의 요청을 표시합니다(추가, 이름 바꾸기, 취소, 삭제). </dd>
<dt>상태</dt>
<dd>이 필드는 요청의 상태를 표시합니다. 승인자가 요청을 승인하거나 거부합니다. 요청이 승인되기를 기다리고 있습니다. 사용자가 요청을 취소합니다(승인됨, 거부됨, 보류 중, 취소됨). </dd>
<dt>Id_User</dt>
<dd>사용자 이름</dd>
<dt>User_name</dt> 
<dd>요청을 수행하는 사용자입니다. </dd>
<dt>Manager_Approval</dt>
<dd>요청이 관리자에 의해 승인된 날짜입니다.
<dt>Access_Approval</dt>
<dd>요청이 그룹 관리자에 의해 승인된 날짜입니다. </dd>
</dl>

## 키 관리
{: #keymgmt}

키 인증서 관리 오퍼레이션을 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Name</dt>
<dd>이벤트의 유형입니다(키 작성 중, 인증서 작성 중, 인증서 삭제 중). </dd>
<dt>인증서/키 이름</dt>
<dd>사용된 인증서 이름 또는 키 이름입니다. </dd>
<dt>Key_Mgmt_Message</dt> 
<dd>실행된 명령입니다(키 "key name" 작성 중, 인증서 "certificate name" 작성 중, 인증서 "certificate name" 구성 삭제됨). </dd>
<dt>대상 IP</dt>
<dd>세션의 대상입니다.
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다. </dd>
</dl>

## 시스템 알림
{: #systemnotifications}

소프트웨어 업데이트 배치 창 또는 알림 구독의 구성과 관련된 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Type</dt>
<dd>이벤트의 유형입니다(SECURITY_RUNTIME).
<ul>
<li> SECURITY_MGMT_CONFIG: Create Window [id]. </li>
<li> SECURITY_MGMT_CONFIG: Update Window [id]. </li>
<li> SECURITY_MGMT_CONFIG: Delete Window [id]. </li>
<li> SECURITY_MGMT_CONFIG: Create Subscription [id]. </li>
<li> SECURITY_MGMT_CONFIG: Update Subscription [id]. </li>
<li> SECURITY_MGMT_CONFIG: Delete Susbscription [id]. </li>
<li> SECURITY_MGMT_CONFIG: Create Topic Reply [id]. </li>
</ul>
</dd>
<dt>사용자</dt> 
<dd>오퍼레이션을 시작한 사용자입니다.
<dt>메시지</dt>
<dd>실행된 명령입니다.
<ul>
<li>Create Window [id]: Creates 유지보수 업데이트를 위한 창을 작성합니다. 업데이트 창 로그는 사용자가 환경에 대한 업데이트 창을 관리(작성)할 때 생성됩니다. 업데이트 창은 블랙아웃이며 배치 작업에 유용한 창입니다. 이는 고객이 배치를 승인하고 스케줄할 필요 없는 자동 배치를 허용하거나 허용하지 않는 경우입니다.
</li>
<li>Update Window [id]: Updates 유지보수 업데이트 창을 업데이트합니다. 이 이벤트는 사용자가 환경에 대한 유지보수 업데이트 창을 업데이트할 때 생성됩니다.
</li>
<li>Delete Window [id]: 업데이트 창을 삭제합니다. 이 이벤트는 사용자가 환경에 대한 업데이트 창을 위임하는 경우 생성됩니다.
</li>
<li>Create Subscription [id]: Creates 이벤트 구독을 작성합니다. 이벤트 구독 감사 로그는 사용자가 업데이트 또는 인시던트 이벤트에 대한 구독을 작성할 때 생성됩니다. 이는 해당 시스템에서 무슨 일이 생기면 알릴 수 있게 됩니다.</li>
<li>Update Subscription [id]: Updates 이벤트 구독을 업데이트합니다. 사용자가 업데이트 또는 인시던트 이벤트에 대한 구독을 업데이트할 때 이벤트가 생성됩니다. </li>
<li>Delete Subscription [id]: Delete 이벤트 구독을 삭제합니다. 이 이벤트는 사용자가 업데이트 또는 인시던트 이벤트에 대한 구독을 삭제할 때 생성됩니다. </li>
<li>Create Topic Reply [id]: Reply 토픽에 응답합니다. 토픽 응답 감사 로그는 고객이 시스템을 중단하는 업데이트를 승인하고 스케줄링할 때 생성됩니다.</li>
</ul>
</dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다(이벤트를 생성한 서버의 IP 주소/호스트 이름). </dd>
</dl>

## Bluemix 플랫폼 관리
{: #platformadmin}

명령행, REST API 또는 Bluemix 사용자 인터페이스를 사용한 Bluemix 플랫폼 관련 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Type</dt>
<dd>이벤트의 유형입니다(SECURITY_RUNTIME).
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY: 특정 사용자 ID에 대한 신임 정보의 수정과 관련된 이벤트입니다.
</li>
<li>SECURITY_MGMT_RESOURCE: 리소스 작성, 삭제, 리소스의 속성 변경과 같은 리소스 관리 이벤트입니다.
</li>
<li>SECURITY_MGMT_POLICY: 액세스 제어 목록의 작성과 같은 보안 정책 관리와 관련된 이벤트입니다. </li>
<li>SECURITY_RUNTIME: 보안 서버 시작 및 중지와 같은 런타임 이벤트입니다.
</li>
<li>SECURITY_RESOURCE_ACCESS: 리소스에 대한 모든 액세스를 기록하는 이벤트입니다. 예를 들면 파일에 대한 모든 액세스, 특정 웹 페이지에 대한 모든 HTTP 요청/응답, 중요 데이터베이스 테이블에 대한 모든 액세스 등이 있습니다.
</li>
</ul>
</dd>
<dt>사용자</dt> 
<dd>오퍼레이션을 시작한 사용자입니다.
<dt>대상</dt> 
<dd>엔티티 ID 및 오퍼레이션의 결과와 같은, 실행된 오퍼레이션의 세부사항입니다. 예를 들어 다음과 같습니다.<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]’). 사용자가 username=equaranta 및 id=ca3a811f-1778-4103-9553-537788ed4c4e를 사용하여 작성되었습니다.
</li>
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}'). 이름이 ops.reports.read인 그룹이 수정되었으며
결과 멤버십은 ID 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e입니다.
</li>
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'. 사용자가 ID 값 5cd5f412-4bbb- 4c44-b44b-713a5bc6144를 사용하여 삭제되었습니다.
</li>
</ul>
</dd>
<dt>메시지</dt>
<dd>오퍼레이션이 수행된 엔티티(메시지 문자열), 또는 오퍼레이션의 표준 http 리턴 코드입니다(숫자 값). </dd>
<dt>Bluemix_Platform_Component</dt>
<dd>컴포넌트 이름입니다. </dd>
<dt>로그 소스</dt>
<dd>이벤트의 호스트 이름/IP 주소입니다. </dd>
<dt>소스</dt>
<dd>이벤트의 소스이며, 예를 들면 IP 주소가 있습니다. </dd>
<dt>데이터</dt>
<dd>추가 세부사항입니다. </dd>
</dl>

## 운영 체제 관리
{: #osadmin}

실패(예: Bosh 에이전트 배치 실패 또는 서비스가 시작되지 않음)를 진단하는 데 도움을 줄 수 있는, Bluemix가 생성한 이벤트를 보고합니다. 

### 데이터 필드

<dl>
<dt>로그 소스 시간</dt>
<dd>이벤트가 발생한 날짜입니다. </dd>
<dt>Event_Name</dt>
<dd>이벤트의 유형입니다(키 작성 중, 인증서 작성 중, 인증서 삭제 중). </dd>
<dt>BMX_key</dt>
<dd>오퍼레이션의 유형입니다(BMX_executed_command, BMX_access_unauthorized, BMX_unsuccessful_delete, BMX_sudoers_folder, BMX_Identity_shadow, BMX_extended_attribute, BMX_sudoers). </dd>
<dt>auid</dt> 
<dd>로그인한 사용자의 소스 사용자 ID입니다(예: auid=0은 루트, auid=1000은 vcap, auid= 55044는 ldap 사용자). </dd>
<dt>uid</dt>
<dd>명령이 실행되는 대상 사용자 ID입니다(예: auid=55044가 로그인한 상태이며 명령을 실행하기 전에 “sudo su”(root) -> uid=0을 수행함).
<dt>exe_key</dt>
<dd>실행된 명령입니다. </dd>
<dt>소스 IP</dt>
<dd>사용자가 명령을 시작한 IP 주소입니다. </dd>
<dt>로그 소스</dt>
<dd>이벤트의 소스입니다. </dd>
</dl>
