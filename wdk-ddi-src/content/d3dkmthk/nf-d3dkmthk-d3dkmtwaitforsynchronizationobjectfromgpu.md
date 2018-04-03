---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObjectFromGpu
title: D3DKMTWaitForSynchronizationObjectFromGpu function
author: windows-driver-content
description: D3DKMTWaitForSynchronizationObjectFromGpu waits for a monitored fence to reach a certain value before processing subsequent context commands.
old-location: display\d3dkmtwaitforsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: 93705446-8B87-46DD-9CFE-DD0473DEE6B6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTWaitForSynchronizationObjectFromGpu, D3DKMTWaitForSynchronizationObjectFromGpu function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObjectFromGpu, display.d3dkmtwaitforsynchronizationobjectfromgpu
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
-	D3DKMTWaitForSynchronizationObjectFromGpu
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTWaitForSynchronizationObjectFromGpu function


## -description


<b>D3DKMTWaitForSynchronizationObjectFromGpu</b> waits for a monitored fence to reach a certain value before processing subsequent context commands.
<div class="alert"><b>Note</b>  For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="https://msdn.microsoft.com/library/windows/hardware/ff547255">D3DKMTWaitForSynchronizationObject</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547262">D3DKMTWaitForSynchronizationObject2</a> callbacks are deprecated and will eventually be removed. </div><div> </div>

## -parameters




### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU

TBD




#### - pData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906811">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a> structure that describes the operation.


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




## -remarks



This function semantics are similar to existing <a href="https://msdn.microsoft.com/library/windows/hardware/ff547262">D3DKMTWaitForSynchronizationObject2</a> call, except that this function also supports monitored fence objects and an array of monitored fence values to wait for.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547255">D3DKMTWaitForSynchronizationObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547262">D3DKMTWaitForSynchronizationObject2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906811">D3DKMT_WAITFORSYNCHRONIZATIONOBJECTFROMGPU</a>
 

 

