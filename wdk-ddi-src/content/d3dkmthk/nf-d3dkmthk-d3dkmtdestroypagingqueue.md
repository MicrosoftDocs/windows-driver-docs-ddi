---
UID: NF:d3dkmthk.D3DKMTDestroyPagingQueue
title: D3DKMTDestroyPagingQueue function
author: windows-driver-content
description: D3DKMTDestroyPagingQueue waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.
old-location: display\d3dkmtdestroypagingqueue.htm
old-project: display
ms.assetid: 470563BD-F185-4CA2-B4AD-06E1AABD36AD
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTDestroyPagingQueue, D3DKMTDestroyPagingQueue function [Display Devices], d3dkmthk/D3DKMTDestroyPagingQueue, display.d3dkmtdestroypagingqueue
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
-	D3DKMTDestroyPagingQueue
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyPagingQueue function


## -description


<b>D3DKMTDestroyPagingQueue</b> waits for a paging queue to finish all operations queued to it, and destroys it along with the associated sync object.


## -parameters




### -param Arg1

TBD




#### - pData [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906321">D3DDDI_DESTROYPAGINGQUEUE</a> structure that describes the operation.


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
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -remarks



In addition to <b>hPagingQueue</b>, this device driver interface (DDI) invalidates <b>hSyncObject</b> and <b>FenceValueCPUVirtualAddress</b> values returned from <a href="https://msdn.microsoft.com/library/windows/hardware/dn906771">D3DKMTCreatePagingQueue</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906321">D3DDDI_DESTROYPAGINGQUEUE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906771">D3DKMTCreatePagingQueue</a>
 

 

