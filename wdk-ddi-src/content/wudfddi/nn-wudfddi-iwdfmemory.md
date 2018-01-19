---
UID: NN:wudfddi.IWDFMemory
title: IWDFMemory
author: windows-driver-content
description: The IWDFMemory interface exposes the framework memory object that provides access to a memory block.
old-location: wdf\iwdfmemory.htm
old-project: wdf
ms.assetid: 8746eb43-7a6e-4e1d-b8fb-c8b7891295d6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
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
req.alt-api: IWDFMemory
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFMemory interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFMemory</b> interface exposes the framework memory object that provides access to a memory block.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFMemory</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFMemory</b> also has these types of members:

The <b>IWDFMemory</b> interface has these methods.

The <a href="https://msdn.microsoft.com/d8e56186-f801-4684-8919-236d2429310f">CopyFromBuffer</a> method safely copies data from the specified source buffer to a memory object.

The <a href="https://msdn.microsoft.com/29b77215-9c7e-47f2-8c94-0bcd733f54a2">CopyFromMemory</a> method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.

The <a href="https://msdn.microsoft.com/c5b34168-b3b8-4559-8b41-982f0a66f01d">CopyToBuffer</a> method safely copies data from a memory object to the specified target buffer.

The <a href="https://msdn.microsoft.com/136aa2af-e3bf-48b6-9511-348510eedfb5">GetDataBuffer</a> method retrieves the data buffer that is associated with a memory object.

The <a href="https://msdn.microsoft.com/1ed699a3-20e5-4a1c-bce0-5a681bac9c39">GetSize</a> method retrieves the size of the data buffer that is associated with a memory object.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>. 

 


## -members
The <b>IWDFMemory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560142">IWDFMemory::CopyFromBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/d8e56186-f801-4684-8919-236d2429310f">CopyFromBuffer</a> method safely copies data from the specified source buffer to a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560145">IWDFMemory::CopyFromMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/29b77215-9c7e-47f2-8c94-0bcd733f54a2">CopyFromMemory</a> method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560148">IWDFMemory::CopyToBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/c5b34168-b3b8-4559-8b41-982f0a66f01d">CopyToBuffer</a> method safely copies data from a memory object to the specified target buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560152">IWDFMemory::GetDataBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/136aa2af-e3bf-48b6-9511-348510eedfb5">GetDataBuffer</a> method retrieves the data buffer that is associated with a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560156">IWDFMemory::GetSize</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/1ed699a3-20e5-4a1c-bce0-5a681bac9c39">GetSize</a> method retrieves the size of the data buffer that is associated with a memory object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560162">IWDFMemory::SetBuffer</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>. 

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/d8e56186-f801-4684-8919-236d2429310f">CopyFromBuffer</a> method safely copies data from the specified source buffer to a memory object.

The <a href="https://msdn.microsoft.com/29b77215-9c7e-47f2-8c94-0bcd733f54a2">CopyFromMemory</a> method safely copies data from the specified source buffer and prevents overruns that the copy operation might otherwise cause.

The <a href="https://msdn.microsoft.com/c5b34168-b3b8-4559-8b41-982f0a66f01d">CopyToBuffer</a> method safely copies data from a memory object to the specified target buffer.

The <a href="https://msdn.microsoft.com/136aa2af-e3bf-48b6-9511-348510eedfb5">GetDataBuffer</a> method retrieves the data buffer that is associated with a memory object.

The <a href="https://msdn.microsoft.com/1ed699a3-20e5-4a1c-bce0-5a681bac9c39">GetSize</a> method retrieves the size of the data buffer that is associated with a memory object.

The <a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a> method assigns a specified buffer to a memory object that a driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>. 

 


## -remarks
