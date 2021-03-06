﻿---
title: 在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄
TOCTitle: 在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/zh-tw/library/Gg399027(v=OCS.15)
ms:contentKeyID: 49292647
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄

 

_**上次修改主題的時間：** 2012-11-01_

如果您要建立新的語音原則，請依照下列步驟執行。如果您要編輯語音原則，請參閱＜[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)＞中的程序。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>每一個語音原則都必須至少有一個相關聯的公用交換電話網路 (PSTN) 使用方式記錄。若要查看 Enterprise Voice 部署中所有可用 PSTN 使用方式記錄的清單，請參閱＜<a href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中檢視 PSTN 使用方式記錄</a>＞。</td>
</tr>
</tbody>
</table>


## 若要建立語音原則

1.  以 RTCUniversalServerAdmins 群組成員或者 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成員的身分登入電腦。如需詳細資料，請參閱[在 Lync Server 2013 中委派設定權限](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。如需可用於啟動 Lync Server 控制台的不同方法的詳細資料，請參閱[開啟 Lync Server 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **\[語音路由\]** 和 **\[語音原則\]**。

4.  在 **\[語音原則\]** 頁面上，按一下 **\[新增\]**，然後為新原則選取範圍：
    
      - **網站原則**適用於整個網站，但指派給使用者原則的任何使用者或群組除外。如果您選取 \[站台\] 做為原則範圍，請從 **\[選取站台\]** 對話方塊選擇網站。如果已建立網站的語音原則，則該網站不會出現在 **\[選取站台\]** 對話方塊。
    
      - **使用者原則**可套用至指定的使用者或群組。

5.  如果語音原則範圍是 \[使用者\]，請在 **\[名稱\]** 欄位中輸入原則的描述性名稱。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果語音原則範圍是 [站台]，則 <strong>[新語音原則]</strong> 的 <strong>[名稱]</strong> 欄位中會預先填入網站名稱，而且無法變更。</td>
    </tr>
    </tbody>
    </table>


6.  (選用) 為語音原則輸入其他描述性資訊。

7.  選取或清除下列核取方塊，即可啟用或停用此語音原則的每一項 **\[撥號功能\]**。
    
      - **\[語音信箱逸出\]** 可避免來電在設定了同步響鈴，且電話已關機、沒電或不在服務範圍內時，立即路由到使用者的行動電話語音信箱系統。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>此功能只可透過 Lync Server 管理命令介面 設定</td>
        </tr>
        </tbody>
        </table>
    
      - **\[來電轉接\]** 可讓使用者將來電轉接到其他電話與用戶端裝置。Lync Server 2013 針對來電轉接提供多種設定選項。例如若某公司不想讓來電向外轉接到 PSTN，管理員可套用特殊語音原則來部署此限制。預設為啟用。
    
      - **\[委派\]** 可讓使用者指定其他使用者代表他們來傳送及接收通話。在 Lync Server 2013 中，代理人可設定同時響鈴，讓主管的來電能夠撥打所有代理人的同時響鈴目標。這項功能給予代理人相當大的彈性，方便代理人回應轉接給主管的來電。預設為啟用。
    
      - **\[通話轉接\]** 可讓使用者將通話轉接給其他使用者。預設為啟用。
    
      - **\[通話駐留\]** 可讓使用者將通話駐留成保留狀態，然後接聽來自不同電話或用戶端的通話。預設為停用。
    
      - **\[同時響鈴\]** 可讓來電在更多電話 (例如行動電話) 或其他端點裝置上響起鈴聲。Lync Server 2013 針對來電轉接提供多種設定選項。預設為啟用。
    
      - **\[小組通話\]** 可讓所定義小組的使用者接聽該小組其他成員的通話。預設為啟用。
    
      - **\[PSTN 重新路由\]** 可在 WAN 擁塞或無法使用時，將被指派此原則的使用者打給其他企業使用者的電話以公用交換電話網路 (PSTN) 重新路由。預設為啟用。
    
      - **頻寬原則覆寫**可讓系統管理員覆寫對於特定使用者之通話許可控制原則的決定。預設為停用。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>只會針對打給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。工作階段建立完畢後，便可準確地記錄頻寬使用量。為順利做出適宜的通話許可控制決策，請勿頻繁使用此設定，能不用就不用。</td>
        </tr>
        </tbody>
        </table>
    
      - **\[惡意來電追蹤\]** 可讓使用者使用用戶端 UI 來回報惡意來電 (如炸彈威脅)，此舉會在詳細通話記錄 (CDR) 中將通話標上旗標。預設為停用。

8.  若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：
    
      - 若要從 Enterprise Voice 部署中所有可用 PSTN 使用方式記錄的清單中選擇一筆或多筆記錄，請按一下 \[選取\]。反白顯示想要與此語音原則關聯的記錄，然後按一下 \[確定\]。
    
      - 若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **\[移除\]**。
    
      - 若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：
        
        1.  按一下 **\[新增\]**。
        
        2.  在 **\[名稱\]** 欄位中，輸入記錄的唯一描述性名稱。例如，您可能會想要針對 Redmond 的全職員工建立一個名為 **Redmond** 的 PSTN 使用方式記錄，並針對臨時員工建立另一個名為 **RedmondTemps** 的 PSTN 使用方式記錄。
            
            <table>
            <thead>
            <tr class="header">
            <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td>在 Enterprise Voice 部署內，PSTN 使用方式記錄名稱必須是唯一的。儲存記錄之後，就無法編輯 <strong>[名稱]</strong> 欄位。</td>
            </tr>
            </tbody>
            </table>
        
        3.  使用下列任何一種方法來關聯及設定此 PSTN 使用方式記錄的路由：
            
              - 若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 \[選取\]，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 \[確定\]。
            
              - 若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 \[移除\]。
            
              - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **\[新增\]**。如需詳細資訊，請參閱＜[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)＞。
            
              - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **\[顯示詳細資料\]**。如需詳細資訊，請參閱＜[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)＞。
        
        4.  按一下 **\[確定\]**。
    
      - 若要編輯已與此語音原則關聯的 PSTN 使用方式記錄，請執行下列動作：
        
        1.  反白顯示想要編輯的 PSTN 使用方式記錄，然後按一下 \[顯示詳細資料\]。
        
        2.  使用下列任何一種方法來關聯及設定此 PSTN 使用方式記錄的路由：
            
              - 若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **\[選取\]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **\[確定\]**。
            
              - 若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 \[移除\]。
            
              - 若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **\[新增\]**。如需詳細資訊，請參閱＜[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)＞。
            
              - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 \[顯示詳細資料\]。如需詳細資訊，請參閱＜[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)＞。
        
        3.  按一下 \[確定\]。

9.  排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412908.important(OCS.15).gif" title="important" alt="important" />重要事項：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>PSTN 使用方式記錄列在語音原則中的順序十分重要。Lync Server 會從上到下周遊清單。建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</td>
    </tr>
    </tbody>
    </table>


10. 若要為此語音原則對應及設定來電轉接與同時響鈴的 PSTN 使用方式記錄，請執行下列任何一項動作：
    
      - 要將同一個來電轉接和同時響鈴的 PSTN 使用方式記錄當作此語音原則使用，請從下拉式功能表選擇 \[使用來電 PSTN 使用方式路由\] 選項。
    
      - 若只要讓內部 Lync 使用者使用來電轉接與同時響鈴功能，請從下拉式功能表選擇 \[只路由至內部 Lync 使用者\] 選項。來電不會轉接到外部 PSTN 號碼。
    
      - 要為此語音原則指定其他來電轉接和同時響鈴的 PSTN 使用方式記錄，請從下拉式功能表選擇 \[使用自訂 PSTN 使用方式路由\]。此選項會顯示控制項，讓您選擇現有的 PSTN 使用方式記錄，或為來電轉接和同時響鈴建立專用的新 PSTN 使用方式記錄。
        
          - 若要從來電轉接與同時響鈴的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 \[選取\]。反白顯示想要與此來電轉接與同時響鈴原則建立關聯的記錄，然後按一下 **\[確定\]**。
        
          - 若要從此來電轉接與同時響鈴原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 \[移除\]。
        
          - 要定義新的 PSTN 使用方式記錄，並與此來電轉接與同時響鈴原則建立關聯，請執行下列動作：
            
            1.  按一下 \[新增\]。
            
            2.  在 \[名稱\] 欄位中，輸入記錄的唯一描述性名稱。
                
                <table>
                <thead>
                <tr class="header">
                <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
                </tr>
                </thead>
                <tbody>
                <tr class="odd">
                <td>在 Enterprise Voice 部署內，PSTN 使用方式記錄名稱必須是唯一的。儲存記錄之後，就無法編輯 [名稱] 欄位。</td>
                </tr>
                </tbody>
                </table>
            
            3.  使用下列任何一種方法來關聯及設定此 PSTN 使用方式記錄的路由：
                
                  - 若要從 Enterprise Voice 部署中所有可用 PSTN 使用方式記錄的清單中選擇一筆或多筆記錄，請按一下 \[選取\]。反白顯示想要與此語音原則關聯的記錄，然後按一下 \[確定\]。
                
                  - 若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **\[移除\]**。
                
                  - 若要定義新的路由，並與此 PSTN 使用方式記錄建立關聯，請按一下 \[新增\]。如需詳細資訊，請參閱＜[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)＞。
                
                  - 若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **\[顯示詳細資料\]**。如需詳細資訊，請參閱＜[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)＞。
            
            4.  按一下 **\[確定\]**。
        
          - 若要編輯已與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：
            
            1.  反白顯示想要編輯的 PSTN 使用方式記錄，然後按一下 **\[顯示詳細資料\]**。
            
            2.  使用下列任何一種方法建立關聯及設定此 PSTN 使用方式記錄的路由：
                
                  - 要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 \[選取\]，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 \[確定\]。
                
                  - 若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **\[移除\]**。
                
                  - 若要定義新的路由，並與此 PSTN 使用方式記錄建立關聯，請按一下 \[新增\]。如需詳細資訊，請參閱＜[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)＞。
                
                  - 若要編輯已與此 PSTN 使用方式記錄建立關聯的路由，請反白顯示路由，然後按一下 \[顯示詳細資料\]。如需詳細資訊，請參閱＜[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)＞。
            
            3.  按一下 **\[確定\]**。

11. (選用) 輸入號碼來測試語音原則，然後按一下 **\[執行\]**。測試結果會顯示於 **\[要測試的轉譯號碼\]** 底下。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>您可以儲存尚未通過測試的語音原則，稍後再加以重新設定。如需詳細資訊，請參閱＜<a href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</a>＞。</td>
    </tr>
    </tbody>
    </table>


12. 按一下 \[確定\]。

13. 在 **\[語音原則\]** 頁面上，依序按一下 **\[認可\]** 和 **\[全部認可\]**。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398811.note(OCS.15).gif" title="note" alt="note" />附註：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>只要建立或修改語音原則，就必須執行 <strong>[全部認可]</strong> 命令來發行設定變更。如需詳細資訊，請參閱操作文件中的＜<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中發佈擱置變更至語音路由設定</a>＞。</td>
    </tr>
    </tbody>
    </table>


14. (選用) 語音信箱逸出會偵測到來電已由使用者的行動電話語音信箱立即接聽，並中斷與行動電話語音信箱通話。這樣來電可持續在使用者的其他端點響鈴，讓使用者有時間接聽來電。有關如何設定語音信箱原則的詳細資訊，請參閱＜[在 Lync Server 2013 中設定語音信箱逸出功能](lync-server-2013-configuring-voice-mail-escape.md)＞。

## 請參閱

#### 工作

[在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中檢視 PSTN 使用方式記錄](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中修改語音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中發佈擱置變更至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[在 Lync Server 2013 中設定語音信箱逸出功能](lync-server-2013-configuring-voice-mail-escape.md)  

#### 其他資源

[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)

