---
UID: NF:d3dkmthk.D3DKMTCreateSynchronizationObject2
title: D3DKMTCreateSynchronizationObject2 function
author: windows-driver-content
description: The D3DKMTCreateSynchronizationObject2 function creates a kernel-mode synchronization object.
old-location: display\d3dkmtcreatesynchronizationobject2.htm
old-project: display
ms.assetid: 45849844-a466-4e62-957a-bfe33a464b5a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateSynchronizationObject2, d3dkmthk/D3DKMTCreateSynchronizationObject2, OpenGL_Functions_ba9aa4a0-19e6-40d2-8a17-d22c8756c555.xml, display.d3dkmtcreatesynchronizationobject2, D3DKMTCreateSynchronizationObject2 function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateSynchronizationObject2 is supported beginning with the Windows 7 operating system.
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
-	D3DKMTCreateSynchronizationObject2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTCreateSynchronizationObject2 function


## -description


The <b>D3DKMTCreateSynchronizationObject2</b> function creates a kernel-mode synchronization object.


## -syntax


````
NTSTATUS D3DKMTCreateSynchronizationObject2(
  _Inout_ D3DKMT_CREATESYNCHRONIZATIONOBJECT2 *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a> structure that describes a synchronization object.


## -returns


<b>D3DKMTCreateSynchronizationObject2</b> returns one of the following values:
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
The kernel-mode synchronization object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md">D3DKMTCreateSynchronizationObject2</a> could not complete because of insufficient memory.

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createsynchronizationobject2.md">D3DKMT_CREATESYNCHRONIZATIONOBJECT2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateSynchronizationObject2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

