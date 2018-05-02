---
UID: NN:wudfddi.IWDFRequestCompletionParams
title: IWDFRequestCompletionParams
author: windows-driver-content
description: The IWDFRequestCompletionParams interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or an asynchronous I/O operation completes.
old-location: wdf\iwdfrequestcompletionparams.htm
old-project: wdf
ms.assetid: f297c6e0-927a-4fb3-bab4-00fdd610a684
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFRequestCompletionParams, IWDFRequestCompletionParams interface, IWDFRequestCompletionParams interface,described, UMDFRequestObjectRef_746528f7-b23f-4907-8661-e228fa99df1c.xml, umdf.iwdfrequestcompletionparams, wdf.iwdfrequestcompletionparams, wudfddi/IWDFRequestCompletionParams
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
-	IWDFRequestCompletionParams
product: Windows
targetos: Windows
req.typenames: 
---

# IWDFRequestCompletionParams interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFRequestCompletionParams</b> interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or an asynchronous I/O operation completes.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFRequestCompletionParams</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IWDFRequestCompletionParams</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFRequestCompletionParams</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560296">IWDFRequestCompletionParams::GetCompletedRequestType</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/1977828d-61bb-4649-bfa6-e5e82775258e">GetCompletedRequestType</a> method retrieves the type of operation that the request to be completed contains.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560301">IWDFRequestCompletionParams::GetCompletionStatus</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/8959fc25-2477-485a-aa40-10d6228cb476">GetCompletionStatus</a> method retrieves the completion status of an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560305">IWDFRequestCompletionParams::GetInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/6dd47575-0da3-4038-81aa-ac955c00f08d">GetInformation</a> method retrieves information that is associated with the completion of an I/O request.

</td>
</tr>
</table> 

