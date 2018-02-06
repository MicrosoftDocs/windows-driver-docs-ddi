---
UID: NF:d3dkmthk.D3DKMTSignalSynchronizationObjectFromGpu2
title: D3DKMTSignalSynchronizationObjectFromGpu2 function
author: windows-driver-content
description: D3DKMTSignalSynchronizationObjectFromGpu2 is used to signal a monitored fence.
old-location: display\d3dkmtsignalsynchronizationobjectfromgpu2.htm
old-project: display
ms.assetid: 813193DC-8066-4B98-BC24-7688630AAC1C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTSignalSynchronizationObjectFromGpu2, D3DKMTSignalSynchronizationObjectFromGpu2 function [Display Devices], D3DKMTSignalSynchronizationObjectFromGpu2, display.d3dkmtsignalsynchronizationobjectfromgpu2
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname:
-	D3DKMTSignalSynchronizationObjectFromGpu2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTSignalSynchronizationObjectFromGpu2 function


## -description


<b>D3DKMTSignalSynchronizationObjectFromGpu2</b> is used to signal a monitored fence.When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from GPU packet using <b>D3DKMTSignalSynchronizationObjectFromGpu2</b>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject.md">D3DKMTSignalSynchronizationObject</a> and <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a> callbacks are deprecated and will eventually be removed. 


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTSignalSynchronizationObjectFromGpu2(
  _In_ const D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 *pData
);
````


## -parameters




### -param D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2

TBD



#### - pData [in]

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2.md">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a> structure that provides the details of the requested operation.


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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject2.md">D3DKMTSignalSynchronizationObject2</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_signalsynchronizationobjectfromgpu2.md">D3DKMT_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobjectfromgpu.md">D3DKMTSignalSynchronizationObjectFromGpu</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsignalsynchronizationobject.md">D3DKMTSignalSynchronizationObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSignalSynchronizationObjectFromGpu2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

