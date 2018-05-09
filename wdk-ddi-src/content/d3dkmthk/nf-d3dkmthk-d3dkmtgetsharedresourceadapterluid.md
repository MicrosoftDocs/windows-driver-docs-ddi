---
UID: NF:d3dkmthk.D3DKMTGetSharedResourceAdapterLuid
title: D3DKMTGetSharedResourceAdapterLuid function
author: windows-driver-content
description: Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.
old-location: display\d3dkmtgetsharedresourceadapterluid.htm
old-project: display
ms.assetid: 880bf5bd-eadc-480f-a10c-f6d57f670857
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTGetSharedResourceAdapterLuid, D3DKMTGetSharedResourceAdapterLuid function [Display Devices], d3dkmthk/D3DKMTGetSharedResourceAdapterLuid, display.d3dkmtgetsharedresourceadapterluid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTGetSharedResourceAdapterLuid
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTGetSharedResourceAdapterLuid function


## -description


Maps a shared resource to a locally unique identifier (LUID) that identifies the graphics adapter that the resource was created on.


## -parameters




### -param Arg1

TBD




#### - pLuid [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/jj128344">D3DKMT_GETSHAREDRESOURCEADAPTERLUID</a> structure that describes a shared resource and the graphics adapter that the resource was created on.


## -returns



Returns one of the following values:

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
The mapping was performed successfully.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/jj128344">D3DKMT_GETSHAREDRESOURCEADAPTERLUID</a>
 

 

