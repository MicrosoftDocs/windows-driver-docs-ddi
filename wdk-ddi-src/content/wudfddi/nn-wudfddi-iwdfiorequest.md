---
UID: NN:wudfddi.IWDFIoRequest
title: IWDFIoRequest
description: The IWDFIoRequest interface exposes an I/O request object.
old-location: wdf\iwdfiorequest.htm
tech.root: wdf
ms.assetid: 3104284a-4277-4f05-ae3f-3b2bb3c3437d
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest, IWDFIoRequest interface, IWDFIoRequest interface,described, UMDFRequestObjectRef_65cbf2de-e966-4eb3-8f3f-2012dba23d99.xml, umdf.iwdfiorequest, wdf.iwdfiorequest, wudfddi/IWDFIoRequest
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
-	IWDFIoRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoRequest</b> interface exposes an I/O request object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFIoRequest</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFIoRequest</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559067">IWDFIoRequest::CancelSentRequest</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/1951a2e8-c2f0-42bc-9deb-8d2a049817c4">CancelSentRequest</a> method attempts to cancel the I/O request that the driver previously submitted to an I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406719">Complete</a> method completes an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559074">IWDFIoRequest::CompleteWithInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/43089473-3255-4016-8d51-f5ad4261bd8d">CompleteWithInformation</a> method completes a request with the supplied information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559077">IWDFIoRequest::FormatUsingCurrentType</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/4cbf6d29-bccd-4629-b282-eb5314f9b4f4">FormatUsingCurrentType</a> method formats an I/O request so that the driver can forward it, unmodified, to the next-lower driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/07317157-1222-4b34-89f4-d546818e9851">ForwardToIoQueue</a> method forwards (that is, requeues) an I/O request to one of the calling driver's I/O queues.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559084">IWDFIoRequest::GetCompletionParams</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/aaca14ff-9ea2-43f4-bfa9-9151d855c3af">GetCompletionParams</a> method retrieves the parameters object for the completion of an I/O request object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/1bc6eed2-c6bd-448f-8f78-630cca4cd29a">GetCreateParameters</a> method retrieves the request parameters for a create-type request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559095">IWDFIoRequest::GetDeviceIoControlParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/96de6f7a-da1d-44a6-b1f7-44859312a662">GetDeviceIoControlParameters</a> method retrieves the request parameters for a device I/O control-type request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559099">IWDFIoRequest::GetFileObject</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/2d6567f1-9e2a-405f-ae8d-eb531cc29275">GetFileObject</a> method retrieves a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface that is associated with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/be3f965b-69fe-4d5e-b1b6-3a370603cd7b">GetInputMemory</a> method retrieves the memory object that represents the input buffer in an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559103">IWDFIoRequest::GetIoQueue</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/834d5ee3-b28b-4d75-b0b7-be1f36ace8aa">GetIoQueue</a> method retrieves the I/O queue object that is associated with an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/12862fb2-4cdb-4446-aa20-ec911c9cd65f">GetOutputMemory</a> method retrieves the memory object that represents the output buffer for an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559113">IWDFIoRequest::GetReadParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/3d5691fa-f5dc-4d13-b19c-a169a43aa7b9">GetReadParameters</a> method retrieves the request parameters for a read-type request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559118">IWDFIoRequest::GetRequestorProcessId</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/8bad169a-3a89-460d-9e6e-e8c1994970a8">GetRequestorProcessId</a> method retrieves the identifier of the process that sent an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559124">IWDFIoRequest::GetType</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj991813">GetType</a> method retrieves the type of operation that a request contains.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559130">IWDFIoRequest::GetWriteParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/0627b278-2fd5-4185-8ec9-8b306c6d85a8">GetWriteParameters</a> method retrieves the request parameters for a write-type request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/beb630e7-9667-4bc2-bf35-69db6cf0b104">Impersonate</a> method registers the interface for the method that the framework should call for impersonation.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559139">IWDFIoRequest::IsFrom32BitProcess</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/80e43bd7-9ab9-46b0-a7f3-08c3577be4bc">IsFrom32BitProcess</a> method determines whether a request originated from a 32-bit process.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/73e323a4-d40e-4414-92b7-310bfb0f6457">MarkCancelable</a> method enables the canceling of the I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/f916b414-9cd9-4745-a021-07c810d0d68b">Send</a> method sends a request to the specified I/O target.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559153">IWDFIoRequest::SetCompletionCallback</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/316b8b75-91ca-4866-b66d-3f66f20126df">SetCompletionCallback</a> method registers the interface for the <a href="https://msdn.microsoft.com/1a4787da-2813-4a7a-820a-5c078175aba5">OnCompletion</a> method that the framework should call when an I/O request completes.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559159">IWDFIoRequest::SetInformation</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">SetInformation</a> method sets the size of information for a request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/5a3fa72c-241e-4270-92eb-70f135d79871">UnmarkCancelable</a> method disables the canceling of an I/O request.

</td>
</tr>
</table> 

