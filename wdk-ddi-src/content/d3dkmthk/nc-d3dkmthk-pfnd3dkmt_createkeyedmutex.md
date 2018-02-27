---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX
title: PFND3DKMT_CREATEKEYEDMUTEX
author: windows-driver-content
description: The D3DKMTCreateKeyedMutex function creates a keyed mutex object.
old-location: display\d3dkmtcreatekeyedmutex.htm
old-project: display
ms.assetid: ae9e4771-ba8d-4472-aeb8-04c3f3c59efa
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTCreateKeyedMutex, D3DKMTCreateKeyedMutex callback function [Display Devices], OpenGL_Functions_a8475da1-40bf-4669-9da8-f6bb09c3f905.xml, PFND3DKMT_CREATEKEYEDMUTEX, d3dkmthk/D3DKMTCreateKeyedMutex, display.d3dkmtcreatekeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTCreateKeyedMutex is supported beginning with the Windows 7 operating system.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTCreateKeyedMutex
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_CREATEKEYEDMUTEX callback


## -description


The <b>D3DKMTCreateKeyedMutex</b> function creates a keyed mutex object.


## -prototype


````
NTSTATUS APIENTRY D3DKMTCreateKeyedMutex(
  _Inout_ D3DKMT_CREATEKEYEDMUTEX *pData
);
````


## -parameters




### -param *








#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex.md">D3DKMT_CREATEKEYEDMUTEX</a> structure that describes a keyed mutex object to create. 


## -returns



<b>D3DKMTCreateKeyedMutex</b> returns one of the following values:

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
The keyed mutex object was successfully created. 

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

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createkeyedmutex.md">D3DKMTCreateKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.




## -see-also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex.md">D3DKMT_CREATEKEYEDMUTEX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_CREATEKEYEDMUTEX callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

