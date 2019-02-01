---
UID: NN:wudfddi.IWDFIoRequestCompletionParams
title: IWDFIoRequestCompletionParams (wudfddi.h)
description: The IWDFIoRequestCompletionParams interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or asynchronous I/O operation completes.
old-location: wdf\iwdfiorequestcompletionparams.htm
tech.root: wdf
ms.assetid: 36bed6be-7202-4dff-989d-57d790b8eb52
ms.date: 02/26/2018
ms.keywords: IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams interface, IWDFIoRequestCompletionParams interface,described, UMDFRequestObjectRef_0670626e-575e-482b-bed6-da7d7d86495d.xml, umdf.iwdfiorequestcompletionparams, wdf.iwdfiorequestcompletionparams, wudfddi/IWDFIoRequestCompletionParams
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
-	IWDFIoRequestCompletionParams
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequestCompletionParams interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoRequestCompletionParams</b> interface exposes methods that drivers can use to obtain completion information about an I/O request. Drivers can call these methods after a synchronous or asynchronous I/O operation completes.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequestCompletionParams</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560292">IWDFRequestCompletionParams</a>. <b>IWDFIoRequestCompletionParams</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoRequestCompletionParams</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559057">IWDFIoRequestCompletionParams::GetIoctlParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/59e2cd27-ec10-46e9-aa0d-4a00e2684e76">GetIoctlParameters</a> method retrieves parameters that are associated with the completion of a device I/O control request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559060">IWDFIoRequestCompletionParams::GetReadParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/8f38616e-498b-485e-84c8-de62477b5871">GetReadParameters</a> method retrieves parameters that are associated with the completion of a read request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559062">IWDFIoRequestCompletionParams::GetWriteParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/7161ba67-d94a-4f05-bb8f-a97ef418e580">GetWriteParameters</a> method retrieves parameters that are associated with the completion of a write request.

</td>
</tr>
</table> 

