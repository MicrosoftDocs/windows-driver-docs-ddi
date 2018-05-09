---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromGpu
title: D3DKMTSignalSynchronizationObjectFromGpu function
author: windows-driver-content
description: D3DKMTSignalSynchronizationObjectFromGpu is used to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromgpu.htm
old-project: display
ms.assetid: 5343A7F6-7EFC-4BAE-8D21-CA8FB9B6078A
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMTSignalSynchronizationObjectFromGpu, D3DKMTSignalSynchronizationObjectFromGpu function [Display Devices], d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu, display.d3dkmtsignalsynchronizationobjectfromgpu
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
-	D3DKMTSignalSynchronizationObjectFromGpu
product:
- Windows
targetos: Windows
req.typenames: 
---

# D3DKMTSignalSynchronizationObjectFromGpu function


## -description


<b>D3DKMTSignalSynchronizationObjectFromGpu</b> is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from GPU packet using <a href="https://msdn.microsoft.com/library/windows/hardware/dn906785">D3DKMTSignalSynchronizationObjectFromGpu2</a>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="https://msdn.microsoft.com/library/windows/hardware/ff547219">D3DKMTSignalSynchronizationObject</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff547227">D3DKMTSignalSynchronizationObject2</a> callbacks are deprecated and will eventually be removed.  


## -parameters




### -param D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU

TBD




#### - pData [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn906804">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</a> structure that provides the details of the requested operation.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547219">D3DKMTSignalSynchronizationObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547227">D3DKMTSignalSynchronizationObject2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906785">D3DKMTSignalSynchronizationObjectFromGpu2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906804">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU</a>
 

 

