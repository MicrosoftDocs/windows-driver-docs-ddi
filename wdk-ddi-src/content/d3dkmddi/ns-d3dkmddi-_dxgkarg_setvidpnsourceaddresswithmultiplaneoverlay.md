---
UID: NS:d3dkmddi._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
title: "_DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY"
author: windows-driver-content
description: Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function.
old-location: display\dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay.htm
old-project: display
ms.assetid: 12266cb0-20c1-4077-b3c5-fb902f3805d3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY structure [Display Devices], _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, d3dkmddi/DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, display.dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
---

# _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY structure


## -description


Contains arguments for the <a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.


## -struct-fields




### -field ContextCount

[in] The number of contexts in the array that the <b>Context</b> member specifies.


### -field Context

[in] An array of handles to the contexts that contributed to a display operation.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562052">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure that identifies the type of display operation to perform.


### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.


### -field PlaneCount

The number of overlay planes that the hardware supports.




### -field pPlanes

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780305">DXGK_MULTIPLANE_OVERLAY_PLANE</a> structure that specifies the first overlay plane to display.


### -field Duration

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.

Must be supported by WDDM 1.3 and later drivers. Available starting with Windows 8.1.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562052">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>



<a href="https://msdn.microsoft.com/95108e45-1a3a-4a75-8719-0caadb911469">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>
 

 

