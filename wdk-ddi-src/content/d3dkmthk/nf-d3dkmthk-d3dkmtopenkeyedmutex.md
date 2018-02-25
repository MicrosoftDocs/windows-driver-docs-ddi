---
UID: NF:d3dkmthk.D3DKMTOpenKeyedMutex
title: D3DKMTOpenKeyedMutex function
author: windows-driver-content
description: The D3DKMTOpenKeyedMutex function opens a keyed mutex object.
old-location: display\d3dkmtopenkeyedmutex.htm
old-project: display
ms.assetid: 309a43bf-5fad-409f-83e6-e88361b03827
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , 3, D, D3DKMTOpenKeyedMutex, D3DKMTOpenKeyedMutex function [Display Devices], K, M, O, OpenGL_Functions_6e2179a9-932f-4bd3-b222-4d5f1471636c.xml, T, d, d3dkmthk/D3DKMTOpenKeyedMutex, display.d3dkmtopenkeyedmutex, e, n, p, t, u, x, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTOpenKeyedMutex is supported beginning with the Windows 7 operating system.
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
-	D3DKMTOpenKeyedMutex
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenKeyedMutex function


## -description


The <b>D3DKMTOpenKeyedMutex</b> function opens a keyed mutex object.


## -syntax


````
NTSTATUS D3DKMTOpenKeyedMutex(
  _Inout_ D3DKMT_OPENKEYEDMUTEX *pData
);
````


## -parameters






#### - pData [in, out]

 A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex.md">D3DKMT_OPENKEYEDMUTEX</a> structure that describes a keyed mutex object.


## -returns




      D3DKMTOpenKeyedMutex returns one of the following values:

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
The keyed mutex object was successfully opened. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex.md">D3DKMT_OPENKEYEDMUTEX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenKeyedMutex function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

