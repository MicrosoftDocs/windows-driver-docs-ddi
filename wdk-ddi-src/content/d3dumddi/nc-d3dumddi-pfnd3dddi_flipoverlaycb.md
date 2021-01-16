---
UID: NC:d3dumddi.PFND3DDDI_FLIPOVERLAYCB
title: PFND3DDDI_FLIPOVERLAYCB (d3dumddi.h)
description: The pfnFlipOverlayCb function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.
old-location: display\pfnflipoverlaycb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_FLIPOVERLAYCB callback function"]
ms.keywords: D3Druntime_Functions_68f39dc6-3dd7-4742-81c9-f23874c6c38f.xml, PFND3DDDI_FLIPOVERLAYCB, PFND3DDDI_FLIPOVERLAYCB callback, d3dumddi/pfnFlipOverlayCb, display.pfnflipoverlaycb, pfnFlipOverlayCb, pfnFlipOverlayCb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_FLIPOVERLAYCB
 - d3dumddi/PFND3DDDI_FLIPOVERLAYCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_FLIPOVERLAYCB
product:
 - Windows
---

# PFND3DDDI_FLIPOVERLAYCB callback function


## -description

The <b>pfnFlipOverlayCb</b> function changes the allocation to display on the overlay or indicates to display the other field of the currently displaying allocation, when deinterlacing an interleaved resource.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_flipoverlay">D3DDDICB_FLIPOVERLAY</a> structure that describes how to change the display on the overlay.

## -returns

<b>pfnFlipOverlayCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The display on the overlay object was successfully changed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_OUTOFMEMORY|pfnFlipOverlayCb could not allocate memory that was required for it to complete.|


This function might also return other HRESULT values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_flipoverlay">D3DDDICB_FLIPOVERLAY</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>

