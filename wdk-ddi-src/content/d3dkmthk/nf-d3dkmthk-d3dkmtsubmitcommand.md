---
UID: NF:d3dkmthk.D3DKMTSubmitCommand
title: D3DKMTSubmitCommand function
author: windows-driver-content
description: D3DKMTSubmitCommand is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing.
old-location: display\d3dkmtsubmitcommand.htm
tech.root: display
ms.assetid: E726B4AC-F003-45B3-B467-F123DBE60D87
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTSubmitCommand, D3DKMTSubmitCommand function [Display Devices], d3dkmthk/D3DKMTSubmitCommand, display.d3dkmtsubmitcommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSubmitCommand
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSubmitCommand function


## -description


<b>D3DKMTSubmitCommand</b> is used to submit command buffers on contexts that support graphics processing unit (GPU) virtual addressing. These contexts generate commands directly from user mode, manage their own command buffer pool and don’t make use of the allocation or patch location list.

This function replaces the old <a href="https://msdn.microsoft.com/5841934d-7e0a-4bb8-a7f8-17d8c0af351f">Render</a> function for such contexts and must be used in its place. Contexts that operate in legacy patch mode must continue to use the old <i>Render</i> function.

Although the user mode driver doesn’t generate patch locations, it must still generate a list of primaries, which are being written to. The video memory manager uses the allocation list to determine which primary allocations are being referenced for write by each command buffer. This information is used to synchronize rendering to the primaries with <i>flip</i> operations.

Some kernel mode drivers need information from their user mode driver on how to submit a particular direct memory access (DMA) buffer to their GPU. In Windows Display Driver Model (WDDM) 1.0, this information was sent by the user mode driver to the kernel mode driver through the command buffer. Since DMA buffer are built directly by the user mode driver and submitted to the GPU without modification they can’t be used to send information to the kernel driver anymore. To enable the transfer of information between the user mode and kernel mode drivers, an explicit private driver data buffer has been added to be sent along with a submission. <div class="alert"><b>Note</b>  This private driver data is unidirectional and the kernel mode driver can’t return information to the user mode driver through this buffer.</div>
<div> </div>



## -parameters




### -param D3DKMT_SUBMITCOMMAND

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906806">D3DKMT_SUBMITCOMMAND</a> structure that describes the operation.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The device context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906806">D3DKMT_SUBMITCOMMAND</a>
 

 

