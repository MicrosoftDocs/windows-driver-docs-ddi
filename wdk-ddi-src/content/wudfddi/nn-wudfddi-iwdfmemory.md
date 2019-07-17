---
UID: NN:wudfddi.IWDFMemory
title: IWDFMemory (wudfddi.h)
description: The IWDFMemory interface exposes the framework memory object that provides access to a memory block.
old-location: wdf\iwdfmemory.htm
tech.root: wdf
ms.assetid: 8746eb43-7a6e-4e1d-b8fb-c8b7891295d6
ms.date: 02/26/2018
ms.keywords: IWDFMemory, IWDFMemory interface, IWDFMemory interface,described, UMDFMemoryObjectRef_14266bd8-214b-4244-a96b-9bea5cfa9d84.xml, umdf.iwdfmemory, wdf.iwdfmemory, wudfddi/IWDFMemory
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFMemory"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFMemory interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFMemory</b> interface exposes the framework memory object that provides access to a memory block.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFMemory</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFMemory</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFMemory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copyfrombuffer">IWDFMemory::CopyFromBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copyfrombuffer">CopyFromBuffer</a> method safely copies data from the specified source buffer to a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copyfrommemory">IWDFMemory::CopyFromMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copyfrommemory">CopyFromMemory</a> method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copytobuffer">IWDFMemory::CopyToBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-copytobuffer">CopyToBuffer</a> method safely copies data from a memory object to the specified target buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-getdatabuffer">IWDFMemory::GetDataBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-getdatabuffer">GetDataBuffer</a> method retrieves the data buffer that is associated with a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-getsize">IWDFMemory::GetSize</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-getsize">GetSize</a> method retrieves the size of the data buffer that is associated with a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfmemory-setbuffer">IWDFMemory::SetBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nf-extsfns-idebugfailureanalysis2-setbuffer">SetBuffer</a> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a>. 

</td>
</tr>
</table> 

