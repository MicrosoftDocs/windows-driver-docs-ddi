---
UID: NF:d3dkmthk.D3DKMTCreateDevice
title: D3DKMTCreateDevice function
author: windows-driver-content
description: The D3DKMTCreateDevice function creates a kernel-mode device context.
old-location: display\d3dkmtcreatedevice.htm
old-project: display
ms.assetid: 91f559cc-c84b-450d-b52c-8289e976f991
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTCreateDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTCreateDevice
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

# D3DKMTCreateDevice function



## -description
The <b>D3DKMTCreateDevice</b> function creates a kernel-mode device context.



## -syntax

````
NTSTATUS D3DKMTCreateDevice(
  _Inout_ D3DKMT_CREATEDEVICE *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdevice.md">D3DKMT_CREATEDEVICE</a> structure that describes the kernel-mode device context.


## -returns
<b>D3DKMTCreateDevice</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The device context was successfully created.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatedevice.md">D3DKMTCreateDevice</a> could not complete because of insufficient memory.

 

This function might also return other <b>NTSTATUS</b> values.

The following code example demonstrates how an OpenGL ICD can use <b>D3DKMTCreateDevice</b> to create a kernel-mode device context.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createdevice.md">D3DKMT_CREATEDEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTCreateDevice function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

