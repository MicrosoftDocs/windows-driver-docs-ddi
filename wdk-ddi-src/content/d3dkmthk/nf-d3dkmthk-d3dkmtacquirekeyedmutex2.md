---
UID: NF:d3dkmthk.D3DKMTAcquireKeyedMutex2
title: D3DKMTAcquireKeyedMutex2 function
author: windows-driver-content
description: Acquires a keyed mutex object that includes private data.
old-location: display\d3dkmtacquirekeyedmutex2.htm
old-project: display
ms.assetid: 94ebfeb6-2035-4dd6-bbc9-ba82939b51ec
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmthk/D3DKMTAcquireKeyedMutex2, D3DKMTAcquireKeyedMutex2 function [Display Devices], PFND3DKMT_ACQUIREKEYEDMUTEX2, display.d3dkmtacquirekeyedmutex2, D3DKMTAcquireKeyedMutex2
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
-	D3DKMTAcquireKeyedMutex2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTAcquireKeyedMutex2 function


## -description


Acquires a keyed mutex object that includes private data.


## -syntax


````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTAcquireKeyedMutex2(
  _Inout_ D3DKMT_ACQUIREKEYEDMUTEX2 *pData
);
````


## -parameters





#### - pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_acquirekeyedmutex2.md">D3DKMT_ACQUIREKEYEDMUTEX2</a> structure that specifies the keyed mutex object to acquire. 


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
The keyed mutex object was successfully acquired. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex2.md">D3DKMTAcquireKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table> 

This function might also return other <b>NTSTATUS</b> values.



## -remarks


<b>D3DKMTAcquireKeyedMutex2</b> behaves like the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.



## -see-also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_acquirekeyedmutex2.md">D3DKMT_ACQUIREKEYEDMUTEX2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTAcquireKeyedMutex2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

