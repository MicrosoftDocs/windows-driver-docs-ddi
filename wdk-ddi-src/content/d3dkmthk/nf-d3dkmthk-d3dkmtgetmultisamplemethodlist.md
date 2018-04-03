---
UID: NF:d3dkmthk.D3DKMTGetMultisampleMethodList
title: D3DKMTGetMultisampleMethodList function
author: windows-driver-content
description: The D3DKMTGetMultisampleMethodList function retrieves a list of multiple-sample methods that are used for an allocation.
old-location: display\d3dkmtgetmultisamplemethodlist.htm
old-project: display
ms.assetid: 10084238-dfeb-42a5-9bf0-06cb9b4f440c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTGetMultisampleMethodList, D3DKMTGetMultisampleMethodList function [Display Devices], OpenGL_Functions_8adebfdd-1a02-4e17-8aef-e183587202d2.xml, d3dkmthk/D3DKMTGetMultisampleMethodList, display.d3dkmtgetmultisamplemethodlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTGetMultisampleMethodList
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetMultisampleMethodList function


## -description


The <b>D3DKMTGetMultisampleMethodList</b> function retrieves a list of multiple-sample methods that are used for an allocation.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548039">D3DKMT_GETMULTISAMPLEMETHODLIST</a> structure that describes the list of multiple-sample methods for an allocation.


## -returns



<b>D3DKMTGetMultisampleMethodList</b> returns one of the following values:

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
The list of multiple-sample methods was successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

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
 

This function might also return other NTSTATUS values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548039">D3DKMT_GETMULTISAMPLEMETHODLIST</a>
 

 

