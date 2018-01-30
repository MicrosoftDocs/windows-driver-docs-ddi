---
UID: NF:d3dkmthk.D3DKMTReserveGpuVirtualAddress
title: D3DKMTReserveGpuVirtualAddress function
author: windows-driver-content
description: D3DKMTReserveGpuVirtualAddress reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.
old-location: display\d3dkmtreservegpuvirtualaddress.htm
old-project: display
ms.assetid: 2F8B689C-162C-4C1B-BD45-A154079334D0
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTReserveGpuVirtualAddress function [Display Devices], display.d3dkmtreservegpuvirtualaddress, d3dkmthk/D3DKMTReserveGpuVirtualAddress, D3DKMTReserveGpuVirtualAddress
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTReserveGpuVirtualAddress
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReserveGpuVirtualAddress function


## -description


<b>D3DKMTReserveGpuVirtualAddress</b> reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.


The driver may choose the base GPU virtual address to use for the reservation by specifying a non-NULL value for <b>BaseAddress</b>. The video memory manager will use the specified range if it is available. If the range intersects with an existing range, the operation will fail. The driver may pass a <b>NULL</b> value in the <b>BaseAddress</b> member to let the video memory manager pick a base address.

When the driver chooses to let the video memory manager pick a base address for the GPU virtual address range, it may choose to constrain the range that the video memory manager will consider by specifying non-NULL values for <b>MinimumAddress</b> and <b>MaximumAddress</b>. The video memory manager will ensure that the allocated GPU virtual address range is entirely contained in the range. The driver may specify only a <b>MinimumAddress</b> and the driver will infer the <b>MaximumAddress</b> is the end of the address space. If  only a <b>MaximumAddress</b>  is specified, the <b>MinimumAddress</b> is inferred to be 0.


## -syntax


````
NTSTATUS APIENTRY D3DKMTReserveGpuVirtualAddress(
  _Inout_ D3DDDI_RESERVEGPUVIRTUALADDRESS *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_reservegpuvirtualaddress.md">D3DDDI_RESERVEGPUVIRTUALADDRESS</a> structure that describes the operation.


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


