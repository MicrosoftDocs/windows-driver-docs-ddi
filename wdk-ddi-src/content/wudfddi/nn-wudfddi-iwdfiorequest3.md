---
UID: NN:wudfddi.IWDFIoRequest3
title: IWDFIoRequest3
author: windows-driver-content
description: To obtain the IWDFIoRequest3 interface, drivers call IWDFIoRequest::QueryInterface.
old-location: wdf\iwdfiorequest3.htm
old-project: wdf
ms.assetid: 12F4CDB7-EEA5-49D1-AD41-6F5F0C9ED6C3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest3, IWDFIoRequest3 interface, IWDFIoRequest3 interface, described, umdf.iwdfiorequest3, wdf.iwdfiorequest3, wudfddi/IWDFIoRequest3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest3
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest3 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoRequest3</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest3</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>. <b>IWDFIoRequest3</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoRequest3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451341">GetUserModeDriverInitiatedIo</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451341">GetUserModeDriverInitiatedIo</a> method determines whether an I/O request is marked as initiated by a UMDF driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451345">RetrieveActivityId</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451345">RetrieveActivityId</a> method retrieves the current activity identifier associated with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451350">SetActivityId</a>
</td>
<td align="left" width="63%">

   The 
  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451350">SetActivityId</a> method associates an activity identifier with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451354">SetUserModeDriverInitiatedIo</a> method 
   
  indicates to kernel-mode drivers that sit below the UMDF driver in the same device stack that a particular request should be treated as though it came from a UMDF driver.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558988">IWDFIoRequest2</a>
 

 

