---
UID: NN:wudfddi.IWDFIoTarget2
title: IWDFIoTarget2
author: windows-driver-content
description: To obtain the IWDFIoTarget2 interface, drivers call IWDFIoTarget::QueryInterface.
old-location: wdf\iwdfiotarget2.htm
old-project: wdf
ms.assetid: 52ce1c63-b2cf-4eda-b056-4f1f999110c5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.iwdfiotarget2, IWDFIoTarget2 interface, IWDFIoTarget2 interface, described, IWDFIoTarget2, wudfddi/IWDFIoTarget2, UMDFIoTargetObjectRef_7639fcef-e463-4500-94a0-132b63e1e564.xml, umdf.iwdfiotarget2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoTarget2
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoTarget2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoTarget2</b> interface, drivers call <b>IWDFIoTarget::QueryInterface</b>.


## -members

The <b>IWDFIoTarget2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559182">IWDFIoTarget2::FormatRequestForFlush</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/28509e28-0e81-4531-947c-9ce452564682">FormatRequestForFlush</a> method builds an I/O request for a flush operation but does not send the request to an I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559184">IWDFIoTarget2::FormatRequestForQueryInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/24ce2918-1d9f-41eb-add1-a50b888f0a99">FormatRequestForQueryInformation</a> method formats an I/O request to obtain information about a file, but it does not send the request to an I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559191">IWDFIoTarget2::FormatRequestForSetInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/2bfdc5c6-da5a-43c1-9165-02d6c448a690">FormatRequestForSetInformation</a> method formats an I/O request to set information about a file, but it does not send the request to an I/O target.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/28509e28-0e81-4531-947c-9ce452564682">FormatRequestForFlush</a> method builds an I/O request for a flush operation but does not send the request to an I/O target.

The <a href="https://msdn.microsoft.com/24ce2918-1d9f-41eb-add1-a50b888f0a99">FormatRequestForQueryInformation</a> method formats an I/O request to obtain information about a file, but it does not send the request to an I/O target.

The <a href="https://msdn.microsoft.com/2bfdc5c6-da5a-43c1-9165-02d6c448a690">FormatRequestForSetInformation</a> method formats an I/O request to set information about a file, but it does not send the request to an I/O target.

 

