---
UID: NF:d3dkmthk.D3DKMTOpenAdapterFromLuid
title: D3DKMTOpenAdapterFromLuid function
author: windows-driver-content
description: Maps a locally unique identifier (LUID) to a graphics adapter handle.
old-location: display\d3dkmtopenadapterfromluid.htm
old-project: display
ms.assetid: 1007c8ba-c503-4522-aef8-23b89bec3d62
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTOpenAdapterFromLuid, D3DKMTOpenAdapterFromLuid function [Display Devices], d3dkmthk/D3DKMTOpenAdapterFromLuid, display.d3dkmtopenadapterfromluid
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
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenAdapterFromLuid
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenAdapterFromLuid function


## -description


Maps a locally unique identifier (LUID) to a graphics adapter handle.


## -parameters




### -param D3DKMT_OPENADAPTERFROMLUID

TBD




#### - pAdapter [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780267">D3DKMT_OPENADAPTERFROMLUID</a> structure that describes information that is required to perform the mapping.


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
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780267">D3DKMT_OPENADAPTERFROMLUID</a>
 

 

