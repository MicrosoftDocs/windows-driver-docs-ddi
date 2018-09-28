---
UID: NF:d3dkmthk.D3DKMTOpenNtHandleFromName
title: D3DKMTOpenNtHandleFromName function
author: windows-driver-content
description: From a given graphics adapter name, opens an NT handle to the process.
old-location: display\d3dkmtopennthandlefromname.htm
ms.assetid: bcd33f64-7ad0-4e26-af73-e4f2b1b6e5fb
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTOpenNtHandleFromName, D3DKMTOpenNtHandleFromName callback function [Display Devices], PFND3DKMT_OPENNTHANDLEFROMNAME, PFND3DKMT_OPENNTHANDLEFROMNAME callback, d3dkmthk/D3DKMTOpenNtHandleFromName, display.d3dkmtopennthandlefromname
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
api_name:
-	D3DKMTOpenNtHandleFromName
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenNtHandleFromName function


## -description


From a given graphics adapter name, opens an NT handle to the process.


## -parameters




### -param Arg1






*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406493">D3DKMT_OPENNTHANDLEFROMNAME</a> structure that describes information required to open an NT handle.


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
The function completed successfully.

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



