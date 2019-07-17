---
UID: NN:wudfddi.IWDFIoRequest2
title: IWDFIoRequest2 (wudfddi.h)
description: To obtain the IWDFIoRequest2 interface, drivers call IWDFIoRequest::QueryInterface.
old-location: wdf\iwdfiorequest2.htm
tech.root: wdf
ms.assetid: 6a6285c9-8366-4487-a1c5-38aa24d172a9
ms.date: 02/26/2018
ms.keywords: IWDFIoRequest2, IWDFIoRequest2 interface, IWDFIoRequest2 interface,described, UMDFRequestObjectRef_0aa42362-60ac-4be7-8101-6395a709f420.xml, umdf.iwdfiorequest2, wdf.iwdfiorequest2, wudfddi/IWDFIoRequest2
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFIoRequest2"
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequest2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequest2 interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

To obtain the <b>IWDFIoRequest2</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest2</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>. <b>IWDFIoRequest2</b> also has these types of members:
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getcreateparametersex">IWDFIoRequest2::GetCreateParametersEx</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getcreateparametersex">GetCreateParametersEx</a> method retrieves file creation parameters that are associated with a file that is being created or opened.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-geteffectiveiotype">IWDFIoRequest2::GetEffectiveIoType</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-geteffectiveiotype">GetEffectiveIoType</a> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <b>IWDFIoRequest2</b> interface represents.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getqueryinformationparameters">IWDFIoRequest2::GetQueryInformationParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getqueryinformationparameters">GetQueryInformationParameters</a> method retrieves parameters that are associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ne-wudfddi_types-_wdf_request_type">WdfRequestQueryInformation</a>-typed I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getrequestormode">IWDFIoRequest2::GetRequestorMode</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getrequestormode">GetRequestorMode</a> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getsetinformationparameters">IWDFIoRequest2::GetSetInformationParameters</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getsetinformationparameters">GetSetInformationParameters</a> method retrieves parameters that are associated with a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestsetinformation">WdfRequestSetInformation</a>-typed I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-getstatus">IWDFIoRequest2::GetStatus</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtf/nf-wdtf-iwdtfaction2-getstatus">GetStatus</a> method returns the status of an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-iscanceled">IWDFIoRequest2::IsCanceled</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-iscanceled">IsCanceled</a> method determines whether the I/O manager has attempted to cancel an I/O request.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-isfromusermodedriver">IWDFIoRequest2::IsFromUserModeDriver</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-isfromusermodedriver">IsFromUserModeDriver</a> method indicates whether an I/O request came from a user-mode driver or an application.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-requeue">IWDFIoRequest2::Requeue</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-requeue">Requeue</a> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputbuffer">IWDFIoRequest2::RetrieveInputBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveinputmemory">RetrieveInputMemory</a> method retrieves the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputbuffer">IWDFIoRequest2::RetrieveOutputBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestretrieveoutputbuffer">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputmemory">IWDFIoRequest2::RetrieveOutputMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-retrieveoutputmemory">RetrieveOutputMemory</a> method retrieves the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-reuse">IWDFIoRequest2::Reuse</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-reuse">Reuse</a> method reinitializes a framework request object so that it can be reused.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">IWDFIoRequest2::StopAcknowledge</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfiorequest2-stopacknowledge">StopAcknowledge</a> method informs the framework that the driver has stopped processing a specified I/O request.

</td>
</tr>
</table> 

