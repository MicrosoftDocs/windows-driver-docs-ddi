---
UID: NC:d3dkmthk.PFND3DKMT_CREATEKEYEDMUTEX2
title: PFND3DKMT_CREATEKEYEDMUTEX2
author: windows-driver-content
description: Creates a keyed mutex object that includes private data.
old-location: display\d3dkmtcreatekeyedmutex2.htm
old-project: display
ms.assetid: fedd7aa0-366c-4083-b6d2-692332813b3f
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3DKMTCreateKeyedMutex2, D3DKMTCreateKeyedMutex2 function [Display Devices], PFND3DKMT_CREATEKEYEDMUTEX2, d3dkmthk/D3DKMTCreateKeyedMutex2, display.d3dkmtcreatekeyedmutex2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	D3DKMTCreateKeyedMutex2
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_CREATEKEYEDMUTEX2 callback


## -description


Creates a keyed mutex object that includes private data.


## -prototype


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTCreateKeyedMutex2(
  _Inout_ D3DKMT_CREATEKEYEDMUTEX2 *pData
);
````


## -parameters




### -param *








#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md">D3DKMT_CREATEKEYEDMUTEX2</a> structure that describes a keyed mutex object to create.


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

<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createkeyedmutex2.md">D3DKMTCreateKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.




## -remarks



<b>D3DKMTCreateKeyedMutex2</b> behaves like the <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createkeyedmutex.md">D3DKMTCreateKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

Keyed mutexes created with <b>D3DKMTCreateKeyedMutex2</b> are still compatible with <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a>, <a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_acquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a>, and <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex.md">D3DKMTReleaseKeyedMutex</a> functions.




## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreleasekeyedmutex.md">D3DKMTReleaseKeyedMutex</a>



<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_createkeyedmutex.md">D3DKMTCreateKeyedMutex</a>



<a href="..\d3dkmthk\nc-d3dkmthk-pfnd3dkmt_acquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createkeyedmutex2.md">D3DKMT_CREATEKEYEDMUTEX2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateKeyedMutex2 function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

