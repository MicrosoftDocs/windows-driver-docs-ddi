---
UID: NF:d3dkmthk.D3DKMTWaitForSynchronizationObject2
title: D3DKMTWaitForSynchronizationObject2 function
author: windows-driver-content
description: The D3DKMTWaitForSynchronizationObject2 function inserts a wait for the specified synchronization objects in the specified context stream.
old-location: display\d3dkmtwaitforsynchronizationobject2.htm
old-project: display
ms.assetid: 692d3336-d9cd-438b-a52c-ae4c55070227
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: OpenGL_Functions_4453dc1e-8824-494e-9a74-2d3628f1ff81.xml, display.d3dkmtwaitforsynchronizationobject2, D3DKMTWaitForSynchronizationObject2 function [Display Devices], d3dkmthk/D3DKMTWaitForSynchronizationObject2, D3DKMTWaitForSynchronizationObject2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTWaitForSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
-	D3DKMTWaitForSynchronizationObject2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTWaitForSynchronizationObject2 function


## -description


The <b>D3DKMTWaitForSynchronizationObject2</b> function inserts a wait for the specified synchronization objects in the specified context stream.


## -syntax


````
NTSTATUS APIENTRY D3DKMTWaitForSynchronizationObject2(
  _In_ const D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2 *pData
);
````


## -parameters




### -param D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2

TBD



#### - pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2.md">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a> structure that describes the synchronization objects and context stream that the wait is set up for.


## -returns


<b>D3DKMTWaitForSynchronizationObject2</b> returns one of the following values:
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
The wait was successfully set up.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display context was reset.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_waitforsynchronizationobject2.md">D3DKMT_WAITFORSYNCHRONIZATIONOBJECT2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTWaitForSynchronizationObject2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

