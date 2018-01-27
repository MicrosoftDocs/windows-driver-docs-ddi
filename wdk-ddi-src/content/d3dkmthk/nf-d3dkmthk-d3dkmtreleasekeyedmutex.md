---
UID: NF:d3dkmthk.D3DKMTReleaseKeyedMutex
title: D3DKMTReleaseKeyedMutex function
author: windows-driver-content
description: The D3DKMTReleaseKeyedMutex function releases a keyed mutex object.
old-location: display\d3dkmtreleasekeyedmutex.htm
old-project: display
ms.assetid: c2a50621-fa84-4525-86f7-845e886203fe
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTReleaseKeyedMutex, OpenGL_Functions_16fd3037-2615-49c0-8500-7c93bcda3c9f.xml, display.d3dkmtreleasekeyedmutex, D3DKMTReleaseKeyedMutex, D3DKMTReleaseKeyedMutex function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTReleaseKeyedMutex is supported beginning with the Windows 7 operating system.
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
-	API-MS-Win-DX-D3DKmt-l1-1-0.dll
-	API-MS-Win-DX-D3DKmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
apiname: 
-	D3DKMTReleaseKeyedMutex
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTReleaseKeyedMutex function


## -description


The <b>D3DKMTReleaseKeyedMutex</b> function releases a keyed mutex object.


## -syntax


````
NTSTATUS APIENTRY D3DKMTReleaseKeyedMutex(
  _Inout_ D3DKMT_RELEASEKEYEDMUTEX *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_releasekeyedmutex.md">D3DKMT_RELEASEKEYEDMUTEX</a> structure that specifies the keyed mutex object to release. 


## -returns


<b>D3DKMTReleaseKeyedMutex</b> returns one of the following values:
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
The keyed mutex object was successfully released. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex.md">D3DKMTReleaseKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.



## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_releasekeyedmutex.md">D3DKMT_RELEASEKEYEDMUTEX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTReleaseKeyedMutex function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

