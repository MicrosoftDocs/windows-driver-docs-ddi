---
UID: NF:d3dkmthk.D3DKMTCreatePagingQueue
title: D3DKMTCreatePagingQueue function
author: windows-driver-content
description: D3DKMTCreatePagingQueue is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.
old-location: display\d3dkmtcreatepagingqueue.htm
old-project: display
ms.assetid: B95ADBC5-35CC-486D-A5C7-0950ABF4B70A
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTCreatePagingQueue, D3DKMTCreatePagingQueue function [Display Devices], d3dkmthk/D3DKMTCreatePagingQueue, display.d3dkmtcreatepagingqueue
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
-	D3DKMTCreatePagingQueue
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTCreatePagingQueue function


## -description


<b>D3DKMTCreatePagingQueue</b> is used to create a device paging queue that can be used to synchronize with video memory management operations for the device, such as making the device resource resident.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906792">D3DKMT_CREATEPAGINGQUEUE</a> structure that describes the operation.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906792">D3DKMT_CREATEPAGINGQUEUE</a>
 

 

