---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectNtHandleFromName
title: D3DKMTOpenSyncObjectNtHandleFromName function
author: windows-driver-content
description: D3DKMTOpenSyncObjectNtHandleFromName opens an NT handle for a named shared monitored fence object, similar to what D3DKMTOpenNtHandleFromName does for shared allocations.
old-location: display\d3dkmtopensyncobjectnthandlefromname.htm
ms.assetid: 29EF6C90-E25F-4E03-8834-EC2546B670AA
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMTOpenSyncObjectNtHandleFromName, D3DKMTOpenSyncObjectNtHandleFromName function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectNtHandleFromName, display.d3dkmtopensyncobjectnthandlefromname
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
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
-	D3DKMTOpenSyncObjectNtHandleFromName
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTOpenSyncObjectNtHandleFromName function


## -description


<b>D3DKMTOpenSyncObjectNtHandleFromName</b> opens an NT handle for a named shared monitored fence object, similar to what <a href="https://msdn.microsoft.com/library/windows/hardware/hh439409">D3DKMTOpenNtHandleFromName</a> does for shared allocations.


## -parameters




### -param Arg1






*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906800">D3DKMT_OPENSYNCOBJECTNTHANDLEFROMNAME</a> structure that describes the operation.


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
The operation was performed successfully.

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
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439409">D3DKMTOpenNtHandleFromName</a>
 

 

