---
UID: NC:d3dumddi.PFND3DDDI_DESTROYOVERLAYCB
title: PFND3DDDI_DESTROYOVERLAYCB (d3dumddi.h)
description: The pfnDestroyOverlayCb function disables the overlay hardware and destroys the kernel-mode overlay object.
old-location: display\pfndestroyoverlaycb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DESTROYOVERLAYCB callback function"]
ms.keywords: D3Druntime_Functions_57512079-654f-4858-bd66-984935adec15.xml, PFND3DDDI_DESTROYOVERLAYCB, PFND3DDDI_DESTROYOVERLAYCB callback, d3dumddi/pfnDestroyOverlayCb, display.pfndestroyoverlaycb, pfnDestroyOverlayCb, pfnDestroyOverlayCb callback function [Display Devices]
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
 - PFND3DDDI_DESTROYOVERLAYCB
 - d3dumddi/PFND3DDDI_DESTROYOVERLAYCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DESTROYOVERLAYCB
---

# PFND3DDDI_DESTROYOVERLAYCB callback function


## -description

The <b>pfnDestroyOverlayCb</b> function disables the overlay hardware and destroys the kernel-mode overlay object.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroyoverlay">D3DDDICB_DESTROYOVERLAY</a> structure that contains a handle to the overlay object to be disabled.

## -returns

<b>pfnDestroyOverlayCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The overlay object was successfully disabled.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

This function might also return other HRESULT values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_destroyoverlay">D3DDDICB_DESTROYOVERLAY</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>

