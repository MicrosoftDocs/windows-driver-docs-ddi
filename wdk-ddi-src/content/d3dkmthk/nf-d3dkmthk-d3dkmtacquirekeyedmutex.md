---
UID: NF:d3dkmthk.D3DKMTAcquireKeyedMutex
title: D3DKMTAcquireKeyedMutex function
author: windows-driver-content
description: The D3DKMTAcquireKeyedMutex function acquires a keyed mutex object.
old-location: display\d3dkmtacquirekeyedmutex.htm
old-project: display
ms.assetid: 0d9627c3-ed1d-49d4-bdca-bc0e49efc234
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTAcquireKeyedMutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTAcquireKeyedMutex is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTAcquireKeyedMutex
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTAcquireKeyedMutex function



## -description
The <b>D3DKMTAcquireKeyedMutex</b> function acquires a keyed mutex object.



## -syntax

````
NTSTATUS APIENTRY D3DKMTAcquireKeyedMutex(
  _Inout_ D3DKMT_ACQUIREKEYEDMUTEX *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md">D3DKMT_ACQUIREKEYEDMUTEX</a> structure that specifies the keyed mutex object to acquire. 


## -returns
<b>D3DKMTAcquireKeyedMutex</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The keyed mutex object was successfully acquired. 
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a> could not complete because of insufficient memory.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md">D3DKMT_ACQUIREKEYEDMUTEX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTAcquireKeyedMutex function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

