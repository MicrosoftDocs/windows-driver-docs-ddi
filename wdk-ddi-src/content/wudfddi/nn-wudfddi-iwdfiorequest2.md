---
UID: NN:wudfddi.IWDFIoRequest2
title: IWDFIoRequest2
author: windows-driver-content
description: To obtain the IWDFIoRequest2 interface, drivers call IWDFIoRequest::QueryInterface.
old-location: wdf\iwdfiorequest2.htm
old-project: wdf
ms.assetid: 6a6285c9-8366-4487-a1c5-38aa24d172a9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest2, IWDFIoRequest2 interface, IWDFIoRequest2 interface,described, UMDFRequestObjectRef_0aa42362-60ac-4be7-8101-6395a709f420.xml, umdf.iwdfiorequest2, wdf.iwdfiorequest2, wudfddi/IWDFIoRequest2
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
req.lib: NtosKrnl.lib
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
-	IWDFIoRequest2
product: Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoRequest2</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>. <b>IWDFIoRequest2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoRequest2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558989">IWDFIoRequest2::GetCreateParametersEx</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/bc34d86b-fa0e-419e-9342-61df12a8e484">GetCreateParametersEx</a> method retrieves file creation parameters that are associated with a file that is being created or opened.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558994">IWDFIoRequest2::GetEffectiveIoType</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/76909efd-99ca-4e47-9c81-8a48608c2543">GetEffectiveIoType</a> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <b>IWDFIoRequest2</b> interface represents.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558997">IWDFIoRequest2::GetQueryInformationParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/e189d2f6-ef1c-45ed-8b55-8aae0661a426">GetQueryInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/a883f22e-0d6f-4755-882b-ad5a60a09271">WdfRequestQueryInformation</a>-typed I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/8f918bc4-d2d0-4d5b-93c8-89f02c81a701">GetRequestorMode</a> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559009">IWDFIoRequest2::GetSetInformationParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/44872d92-4a71-4cc7-9f7c-c95477ac3264">GetSetInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>-typed I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559013">IWDFIoRequest2::GetStatus</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a> method returns the status of an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559018">IWDFIoRequest2::IsCanceled</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/68523fcb-bb0d-492f-b6ae-3dab4f6aa637">IsCanceled</a> method determines whether the I/O manager has attempted to cancel an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/17a1e4d8-5438-42b6-b4a5-335e7bd57b1b">IsFromUserModeDriver</a> method indicates whether an I/O request came from a user-mode driver or an application.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559028">IWDFIoRequest2::Requeue</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/1e33f284-6cb9-426f-a900-76b827341927">Requeue</a> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/fa02a787-502c-48a3-a5e1-710d7513c42e">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/32596330-6cd9-4f82-9140-7f9a26cf7932">RetrieveInputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/d17e7435-adc3-4248-a6c9-c7e267504291">RetrieveOutputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559048">IWDFIoRequest2::Reuse</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/21d04633-3b68-4c89-a0b9-81507a1bb6d3">Reuse</a> method reinitializes a framework request object so that it can be reused.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559051">IWDFIoRequest2::StopAcknowledge</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/af4ae2c0-b1e1-45af-bd0e-3b9a91566caa">StopAcknowledge</a> method informs the framework that the driver has stopped processing a specified I/O request.

</td>
</tr>
</table> 

