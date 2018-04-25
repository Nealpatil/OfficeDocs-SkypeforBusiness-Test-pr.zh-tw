﻿---
title: Lync Server 2013：匯出語音路由測試案例
TOCTitle: 匯出語音路由測試案例
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/zh-tw/library/Gg425957(v=OCS.15)
ms:contentKeyID: 49290803
ms.date: 08/10/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中匯出語音路由測試案例

 

_**上次修改主題的時間：** 2012-11-01_

測試案例提供了測試組織中語音路由的方法；定義要撥打的號碼，以及要採用的撥號對應表和語音原則等，然後 Lync Server 就可以驗證在指定的那些條件下，驗證提供的號碼是否可以成功路由至 PSTN 網路。

測試案例 (可以使用 Lync Server 控制台建立) 通常僅儲存在原先建立並執行案例的伺服器上。不過這些測試案例可以匯出為 XML 檔案 (副檔名為 .vtest)，然後匯入其他伺服器。這讓您可以在位於拓撲中不同點之不同電腦上執行相同的測試。

## 若要匯出語音路由測試案例

1.  在 Lync Server 控制台中，依序按一下 **\[語音路由\]** 和 **\[測試語音路由\]** 。

2.  在 **\[測試語音路由\]** 索引標籤上，選取要匯出的測試案例。如果要選取多個測試案例，請按一下要匯出的第一個案例，然後按住 Ctrl 鍵，再選取其他要匯出的案例。

3.  依序按一下 **\[動作\]** 和 **\[匯出測試案例\]** 。

4.  在 **\[另存新檔\]** 對話方塊中，選取要儲存匯出的測試案例的資料夾，然後在 **\[檔案名稱\]** 方塊中輸入產生的 XML 檔案的名稱。請注意，如果您匯出多個測試案例，這些測試案例會全部儲存為單一 XML 檔案。

5.  若要儲存測試案例，按一下 **\[儲存\]** 。

## 請參閱

#### 工作

[在 Lync Server 2013 中改善語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)
