---
UID: NF:d3dkmthk.D3DKMTCreateContextVirtual
title: D3DKMTCreateContextVirtual function
author: windows-driver-content
description: The D3DKMTCreateContextVirtual function creates a kernel mode device context that supports virtual addressing.
old-location: display\d3dkmtcreatecontextvirtual.htm
old-project: display
ms.assetid: 1E95228E-7513-46D2-8402-28CA6D26F3EB
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCreateContextVirtual, D3DKMTCreateContextVirtual function [Display Devices], d3dkmthk/D3DKMTCreateContextVirtual, display.d3dkmtcreatecontextvirtual
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
-	D3DKMTCreateContextVirtual
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTCreateContextVirtual function


## -description


The <b>D3DKMTCreateContextVirtual</b> function creates a kernel mode device context that supports virtual addressing.


## -parameters




### -param Arg1

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906791">D3DKMT_CREATECONTEXTVIRTUAL</a> structure that describes the kernel-mode device context.


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
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
<b>D3DKMTCreateContextVirtual</b> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906791">D3DKMT_CREATECONTEXTVIRTUAL</a>
 

 

