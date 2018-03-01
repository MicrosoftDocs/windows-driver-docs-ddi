---
UID: NF:d3dkmthk.D3DKMTOpenKeyedMutex2
title: D3DKMTOpenKeyedMutex2 function
author: windows-driver-content
description: Opens a keyed mutex object that includes private data.
old-location: display\d3dkmtopenkeyedmutex2.htm
old-project: display
ms.assetid: 33140445-e312-4495-990a-033a87598fa1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTOpenKeyedMutex2, D3DKMTOpenKeyedMutex2 callback function [Display Devices], PFND3DKMT_OPENKEYEDMUTEX2, d3dkmthk/D3DKMTOpenKeyedMutex2, display.d3dkmtopenkeyedmutex2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMTOpenKeyedMutex2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTOpenKeyedMutex2 function


## -description


Opens a keyed mutex object that includes private data.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenKeyedMutex2(
  _Inout_ D3DKMT_OPENKEYEDMUTEX2 *pData
);
````


## -parameters






#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex2.md">D3DKMT_OPENKEYEDMUTEX2</a> structure that describes a keyed mutex object that includes private data.


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

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_openkeyedmutex2.md">D3DKMTOpenKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



<b>D3DKMTOpenKeyedMutex2</b> behaves like the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex2.md">D3DKMT_OPENKEYEDMUTEX2</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_OPENKEYEDMUTEX2 callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

