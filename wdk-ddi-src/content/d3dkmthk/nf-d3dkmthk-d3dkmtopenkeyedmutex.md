---
UID: NF:d3dkmthk.D3DKMTOpenKeyedMutex
title: D3DKMTOpenKeyedMutex function
author: windows-driver-content
description: The D3DKMTOpenKeyedMutex function opens a keyed mutex object.
old-location: display\d3dkmtopenkeyedmutex.htm
old-project: display
ms.assetid: 309a43bf-5fad-409f-83e6-e88361b03827
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTOpenKeyedMutex
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
req.alt-api: D3DKMTOpenKeyedMutex
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

### -param pData [in, out]

 A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex.md">D3DKMT_OPENKEYEDMUTEX</a> structure that describes a keyed mutex object.


## -returns

      D3DKMTOpenKeyedMutex returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The keyed mutex object was successfully opened. 
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped or the display device was reset.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenkeyedmutex.md">D3DKMTOpenKeyedMutex</a> could not complete because of insufficient memory.

 

This function might also return other NTSTATUS values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_openkeyedmutex.md">D3DKMT_OPENKEYEDMUTEX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTOpenKeyedMutex function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

