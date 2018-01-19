---
UID: NF:d3dkmthk.D3DKMTLock2
title: D3DKMTLock2 function
author: windows-driver-content
description: The D3DKMTLock2 function locks an entire allocation or specific pages within an allocation.
old-location: display\d3dkmtlock2.htm
old-project: display
ms.assetid: 033FF321-2617-4AAF-8445-10800411F0B5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTLock2
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
req.alt-api: D3DKMTLock2
req.alt-loc: Gdi32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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

# D3DKMTLock2 function



## -description
The <b>D3DKMTLock2</b> function locks an entire allocation or specific pages within an allocation.



## -syntax

````
NTSTATUS APIENTRY D3DKMTLock2(
  _Inout_ D3DKMT_LOCK2 *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_lock2.md">D3DKMT_LOCK2</a> structure that describes parameters for locking an allocation.


## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The allocation was successfully locked.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_BUSY</b></dt>
</dl>The allocation was currently in use and could not be locked.
<dl>
<dt><b>STATUS_GRAPHICS_TOO_MANY_REFERENCES</b></dt>
</dl>Too many references were pending on the allocation.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_lock2.md">D3DKMT_LOCK2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTLock2 function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

