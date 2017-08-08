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


# 報告詳細資料（依類型）

## 防火牆登入
{: #firewalllogins}

報告 Vyatta 防火牆裝置的管理者登入相關事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生日期。</dd>
<dt>事件名稱</dt>
<dd>事件類型（「使用者無法透過 SSH 登入 - 密碼不正確」、「鑑別失敗」、「已關閉階段作業」、「為使用者已接受密碼」、「為使用者已開啟階段作業」）。</dd>
<dt>低階種類</dt>
<dd>事件詳細資料（「SSH 登入失敗」、「已關閉階段作業」、「主機登入成功」、「已開啟階段作業」）。</dd>
<dt>使用者名稱</dt> 
<dd>啟動階段作業之使用者的認證（使用者名稱）。</dd>
<dt>來源 IP</dt>
<dd>使用者從該處啟動階段作業的 IP 位址。
<dt>目的地 IP</dt>
<dd>階段作業的目標。</dd>
<dt>日誌來源</dt>
<dd>事件來源（產生事件之防火牆的主機名稱）。</dd>
</dl>

## 防火牆拒絕
{: #firewalldenies}

報告因現有防火牆規則而拒絕存取要求時，Vyatta 防火牆裝置所產生的事件。
  
### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期和時間。</dd>
<dt>事件名稱</dt>
<dd>事件類型（「使用者無法透過 SSH 登入 - 密碼不正確」、「鑑別失敗」、「已關閉階段作業」、「為使用者已接受密碼」、「為使用者已開啟階段作業」）。</dd>
<dt>低階種類</dt>
<dd>防火牆拒絕事件的詳細資料</dd>
<dt>來源 IP</dt> 
<dd>從該處啟動網路連線及（或）攻擊的來源 IP 位址。</dd>
<dt>來源埠</dt>
<dd>通訊協定目的地埠。
<dt>目的地 IP</dt>
<dd>階段作業的目標。</dd>
<dt>目的地埠</dt>
<dd>通訊協定目的地埠。</dd>
<dt>通訊協定</dt>
<dd>通訊協定 (tcp/udp)。
<dt>日誌來源</dt>
<dd>事件來源（產生事件之防火牆的主機名稱）。</dd>
<dt>事件計數</dt>
<dd>該類型的事件數目。</dd>
</dl>

## 作業系統登入
{: #oslogin}

報告管理者在 Bluemix 系統上啟動 SSH 階段作業時，作業系統所產生的事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生日期。</dd>
<dt>事件名稱</dt>
<dd>事件類型（使用者空間鑑別、使用者空間鑑別失敗）</dd>
<dt>使用者名稱</dt> 
<dd>啟動鑑別處理程序之使用者的使用者名稱。</dd>
<dt>來源位址</dt>
<dd>使用者從該處啟動階段作業的 IP 位址。
<dt>目的地 IP</dt>
<dd>階段作業的目標。</dd>
<dt>日誌來源</dt>
<dd>事件來源（從該處產生事件之伺服器的主機名稱）。</dd>
</dl>

## 登入伺服器登入 
{: #loginserverlogins}

報告 Bluemix 平台使用者使用指令行、REST API 或 Bluemix 主控台來啟動階段作業時，Bluemix 平台登入元件所產生的事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件名稱</dt>
<dd>事件類型（使用者空間鑑別、使用者空間鑑別失敗）</dd>
<dt>使用者</dt> 
<dd>啟動鑑別處理程序之使用者的使用者 ID。</dd>
<dt>Bluemix 平台元件</dt>
<dd>產生事件的元件 (login_server)。
<dt>訊息類型</dt>
<dd>作業類型（登入、登出）。</dd>
<dt>狀態</dt>
<dd>作業結果（成功/失敗）。</dd>
<dt>日誌來源</dt>
<dd>事件來源。</dd>
</dl>

## 資料庫管理
{: #dbadmin}

報告資料庫管理者對 Bluemix 內部資料庫執行之作業的相關事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件類型</dt>
<dd>事件類型 (SECURITY_RUNTIME)。
<dt>使用者</dt> 
<dd>執行作業之使用者的使用者名稱。下列使用者是定義給資料庫的使用者。
<ul>
<li>UAADB：vcap、root、backup_user。
</li>
<li>CCDB：vcap、ccadmin、backup_user。
</li>
<li>在上述項目之外的使用需要調查執行作業的人員。這可以使用「作業系統管理安全報告」及「作業系統登入安全報告」來完成。
</li>
</ul>
</dd>
<dt>來源</dt> 
<dd>使用者從該處啟動指令的 IP 位址。預期值如下：
<ul>
<li>UAADB - uaa VM 及 nfs_WAL_server VM。
</li>
<li>CCDB - api_worker、clock_global、cloud_controller_ng 及 nsf_WAL_server VM。
</li>
</ul>
</dd>
<dt>DB 陳述式</dt>
<dd>作業類型（所有資料定義陳述式，例如 CREATE、ALTER 及 DROP 陳述式，以及資料修改陳述式，例如 INSERT、UPDATE、DELETE、TRUNCATE 及 COPY FROM）</dd>
<dt>DB 名稱</dt>
<dd>已執行作業的 DB 名稱</dd>
</dl>

## 管理主控台使用者管理
{: #acusermgmt}

報告在 Bluemix 管理主控台上執行的使用者管理活動。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件類型</dt>
<dd>事件類型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_MGMT_REGISTRY：新增使用者 [user ID]
</li>
<li>SECURITY_MGMT_REGISTRY：刪除使用者 [user ID]
</li>
<li>SECURITY_AUTHN_CREDS_MODIFY：新增使用者 [user ID] 的許可權 [permissions]。
</li>
<li>SECURITY_AUTHN_CREDS_MODIFY：移除使用者 [user ID] 的許可權 [permissions]。
</li>
<li>SECURITY_MGMT_CONFIG：建立組織 [name]。
</li>
<li>SECURITY_MGMT_CONFIG：變更組織管理員 [ids]。
</li>
<li>SECURITY_MGMT_CONFIG：將組織 ID [id] 重新命名為新名稱 [name]。
</li>
<li>SECURITY_MGMT_CONFIG：刪除組織 ID [id]。
</li>
<li>SECURITY_MGMT_CONFIG：將組織 [id] 的配額更新為配額 [quotaPlan]。
</li>
</ul>
</dd>
<dt>使用者</dt> 
<dd>已啟動作業的使用者 (LDAP ID)。
<dt>訊息</dt> 
<dd>已執行的指令。
<ul>
<li>新增使用者 [user ID]：新增具有指定 ID 的使用者。</li>
<li>刪除使用者 [user ID]：刪除具有指定 ID 的使用者。</li>
<li>新增許可權 [permissions] 給使用者 [user ID]：新增許可權給指定的使用者。許可權可以包括：ops.admin、ops.login、ops.reports.read、ops.reports.write、ops.catalog.read、ops.catalog.write、ops.users.read 及 ops.user.write。</li>
<li>移除使用者 [user ID] 的許可權 [permissions]：移除許可權 - 移除指定使用者的許可權。許可權可以包括：ops.admin、ops.login、ops.reports.read、ops.reports.write、ops.catalog.read、ops.catalog.write、ops.users.read 及 ops.users.write。</li>
<li>建立組織 [name]：建立具有指定名稱的組織。</li>
<li>變更組織管理員 [ids]：將組織的管理員配置為指定的使用者。</li>
<li>將組織 ID [id] 重新命名為新名稱 [name]：重新命名指定的組織。</li>
<li>刪除使用者 [user ID]：刪除具有指定 ID 的使用者。</li>
<li>刪除組織 ID [id]：刪除指定的組織。</li>
<li>將組織 [id] 的配額更新為配額 [quotaPlan]：更新指定組織的配額方案。方案可以包括：q2GB、q4GB、q8GB、q16GB、q32GB、q64GB、q128GB、q256GB、q512GB。</li>
</ul>
</dd>
<dt>日誌來源</dt>
<dd>事件來源（產生事件之伺服器的 IP 位址/主機名稱）</dd>
</dl>

## 型錄管理
{: #catalogmgmt}

報告在 Bluemix 管理主控台上執行的服務型錄管理活動相關事件。 

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>登錄範本 [id]。讓具有指定 ID 的「樣板」或「運行環境」能夠顯示為所有使用者的「型錄」選項。</dd>
<dd>取消登錄範本 [id]。讓「樣板」或「運行環境」不再顯示為所有使用者的「型錄」選項。</dd>
<dd>將服務方案 [id] 更新為公用 = [ public ]，且可見性 = [ ids ]。更新指定服務方案的可見性。如果公用設為 true，則所有組織都可以看到方案。如果公用設為 false，則可能會提供一組組織 ID，指出可以看到此服務方案的組織。</dd>
<dd>新增服務分配管理系統 [name]。新增具有指定名稱的「服務分配管理系統」。</dd>
<dd>刪除服務分配管理系統 [name]。刪除具有指定名稱的服務分配管理系統。</dd>
<dd>更新建置套件 [id]。更新具有指定 ID 之建置套件的建置套件排序。</dd>
<dt>日誌來源</dt>
<dd>事件來源（產生事件之伺服器的 IP 位址/主機名稱）。</dd>
</dl>

## 安全報告管理
{: #securityreportsmgmt}

報告在管理主控台上執行的安全報告管理活動相關事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dd>事件類型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_DATA_SYNC：將報告 [name] 上傳至種類 [name] 日期 [date]。
刪除具有 ID [id] 的報告
</li>
<li>SECURITY_RESOURCE_ACCESS：下載報告 [name]。
</li>
</ul>
</dd>
<dt>使用者</dt> 
<dd>已啟動作業的使用者。
<dt>訊息</dt> 
<dd>已執行的指令。
<ul>
<li>將報告 [name] 上傳至種類 [name] 日期 [date]：上傳 - 將具有指定檔名及日期的報告上傳至指定的種類。</li>
<li>刪除具有 ID [id] 的報告：刪除 - 刪除具有指定 ID 的報告。</li>
<li>下載報告 [name]: Download - 下載具有指定名稱的報告。</li>
</ul>
</dd>
<dt>日誌來源</dt>
<dd>事件來源（產生事件之伺服器的 IP 位址/主機名稱）。</dd>
</dl>

## 存取檢閱
{: #accessreviews}

報告 Bluemix 環境的特許存取要求，以及 Bluemix 管理者對其的處理作業。 

### 資料欄位

<dl>
<dt>動作名稱</dt>
<dd>指出來自使用者的要求：成為群組的一部分、重新命名使用者 ID、在解雇時予以撤銷、從群組中移除（「新增」、「重新命名」、「撤銷」、「刪除」）。</dd>
<dt>狀態</dt>
<dd>此欄位指出要求的狀態。核准者接受或拒絕要求。要求正在等待核准。使用者取消要求（「已接受」、「已拒絕」、「擱置中」、「已取消」）。</dd>
<dt>使用者 ID</dt>
<dd>使用者名稱</dd>
<dt>使用者名稱</dt> 
<dd>提出要求的使用者。</dd>
<dt>管理員核准</dt>
<dd>管理員核准要求的日期
<dt>存取核准</dt>
<dd>「群組管理員」核准要求的日期。</dd>
</dl>

## 金鑰管理
{: #keymgmt}

報告「金鑰憑證管理」作業。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件名稱</dt>
<dd>事件類型（「建立金鑰」、「建立憑證」、「刪除憑證」）。</dd>
<dt>憑證/金鑰名稱</dt>
<dd>已使用的憑證名稱或金鑰名稱。</dd>
<dt>金鑰管理訊息</dt> 
<dd>已執行的指令（建立金鑰 "key name"、建立憑證 "certificate name"、已刪除憑證 "certificate name" 配置）。</dd>
<dt>目的地 IP</dt>
<dd>階段作業的目標。
<dt>日誌來源</dt>
<dd>事件來源。</dd>
</dl>

## 系統通知
{: #systemnotifications}

報告配置軟體更新部署時間範圍或通知訂閱的相關事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件類型</dt>
<dd>事件類型 (SECURITY_RUNTIME)。
<ul>
<li> SECURITY_MGMT_CONFIG：建立時間範圍 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：更新時間範圍 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：刪除時間範圍 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：建立訂閱 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：更新訂閱 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：刪除訂閱 [id]。
</li>
<li> SECURITY_MGMT_CONFIG：建立主題回覆 [id]。
</li>
</ul>
</dd>
<dt>使用者</dt> 
<dd>已啟動作業的使用者
<dt>訊息</dt>
<dd>已執行的指令。
<ul>
<li>建立時間範圍 [id]: Creates 維護更新的時間範圍。使用者管理（建立）環境的更新時間範圍時，會產生更新時間範圍日誌。更新時間範圍是部署的管制及偏好時間範圍。這是指客戶容許/不容許部署非干擾性的部署作業，而不需要核准及排定它們的時間。
</li>
<li>更新時間範圍 [id]: Updates 維護更新時間範圍。使用者更新環境的維護更新時間範圍時，會產生此事件。</li>
<li>SECURITY_MGMT_CONFIG：刪除更新時間範圍。使用者委派環境的更新時間範圍時，會產生此事件。
</li>
<li>建立訂閱 [id]: Creates 事件訂閱。使用者建立更新事件或突發事件的訂閱時，會產生事件訂閱審核日誌。這樣可在系統上發生事情時通知他們。</li>
<li>更新訂閱 [id]: Updates 事件訂閱。使用者更新更新事件或突發事件的訂閱時，會產生此事件。</li>
<li>刪除訂閱 [id]: Delete 事件訂閱。使用者刪除更新事件或突發事件的訂閱時，會產生此事件。</li>
<li>建立主題回覆 [id]: Reply 主題。客戶核准及排定干擾性更新時，會產生主題回覆審核日誌。</li>
</ul>
</dd>
<dt>日誌來源</dt>
<dd>事件來源（產生事件之伺服器的 IP 位址/主機名稱）。</dd>
</dl>

## Bluemix 平台管理
{: #platformadmin}

報告使用指令行、REST API 或 Bluemix 使用者介面的 Bluemix 平台相關事件。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生日期。</dd>
<dt>事件類型</dt>
<dd>事件類型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY：給定使用者身分的認證修改相關事件。
</li>
<li>SECURITY_MGMT_RESOURCE：資源管理事件（例如資源屬性的建立、刪除及變更）。
</li>
<li>SECURITY_MGMT_POLICY：安全原則管理的相關事件（例如存取控制清單的建立）。</li>
<li>SECURITY_RUNTIME：運行環境事件（例如安全伺服器的啟動及停止）。
</li>
<li>SECURITY_RESOURCE_ACCESS：記錄資源的所有存取的事件。例如，檔案的所有存取、給定網頁的所有 HTTP 要求/回應，以及重要資料庫表格的所有存取。
</li>
</ul>
</dd>
<dt>使用者</dt> 
<dd>已啟動作業的人員
<dt>目標</dt> 
<dd>已執行作業的詳細資料（例如實體 ID 及作業結果）。範例：<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]')。已使用（username=equaranta 及 id = ca3a811f-1778-4103-9553-537788ed4c4e）建立使用者。
</li>
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}')。已修改名稱為 ops.reports.read 的群組，結果的成員資格為 (id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e)。
</li>
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'。已刪除 ID 值 = 5cd5f412-4bbb- 4c44-b44b-713a5bc6144 的使用者。
</li>
</ul>
</dd>
<dt>訊息</dt>
<dd>作業執行所在的實體（訊息字串），或作業的標準 http 回覆碼（數值）。</dd>
<dt>Bluemix 平台元件</dt>
<dd>元件名稱。</dd>
<dt>日誌來源</dt>
<dd>事件來源的主機名稱/IP 位址。</dd>
<dt>來源</dt>
<dd>事件來源，範例為 IP 位址。</dd>
<dt>資料</dt>
<dd>其他詳細資料。</dd>
</dl>

## 作業系統管理
{: #osadmin}

報告由 Bluemix 所產生且有助於診斷失敗的事件（例如，無法部署 Bosh 代理程式，或服務未啟動）。

### 資料欄位

<dl>
<dt>日誌來源時間</dt>
<dd>事件發生的日期。</dd>
<dt>事件名稱</dt>
<dd>事件類型（「建立金鑰」、「建立憑證」、「刪除憑證」）。</dd>
<dt>BMX 金鑰</dt>
<dd>作業類型（BMX_executed_command、BMX_access_unauthorized、BMX_unsuccessful_delete、BMX_sudoers_folder、BMX_Identity_shadow、BMX_extended_attribute、BMX_sudoers）。</dd>
<dt>auid</dt> 
<dd>已登入使用者的來源使用者 ID（例如 auid=0 是 root、auid=1000 是 vcap、auid= 55044 是 ldap 使用者）。</dd>
<dt>uid</dt>
<dd>用來執行指令的目標使用者 ID（例如，執行指令之前，auid=55044 已登入並執行 "sudo su" (root) -> uid=0）。
<dt>exe_key</dt>
<dd>已執行的指令。</dd>
<dt>來源 IP</dt>
<dd>使用者從該處啟動指令的 IP 位址。</dd>
<dt>日誌來源</dt>
<dd>事件來源。</dd>
</dl>
