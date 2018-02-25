---
UID: NF:d3dkmthk.D3DKMTOpenNtHandleFromName
title: D3DKMTOpenNtHandleFromName function
author: windows-driver-content
description: From a given graphics adapter name, opens an NT handle to the process.
old-location: display\d3dkmtopennthandlefromname.htm
old-project: display
ms.assetid: bcd33f64-7ad0-4e26-af73-e4f2b1b6e5fb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 3, D, D3DKMTOpenNtHandleFromName, D3DKMTOpenNtHandleFromName function [Display Devices], F, H, K, M, N, O, PFND3DKMT_OPENNTHANDLEFROMNAME, T, a, d, d3dkmthk/D3DKMTOpenNtHandleFromName, display.d3dkmtopennthandlefromname, e, l, m, n, o, p, r, t"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTOpenNtHandleFromName
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenNtHandleFromName function


## -description


From a given graphics adapter name, opens an NT handle to the process.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenNtHandleFromName(
  _Inout_ D3DKMT_OPENNTHANDLEFROMNAME *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opennthandlefromname.md">D3DKMT_OPENNTHANDLEFROMNAME</a> structure that describes information required to open an NT handle.


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



