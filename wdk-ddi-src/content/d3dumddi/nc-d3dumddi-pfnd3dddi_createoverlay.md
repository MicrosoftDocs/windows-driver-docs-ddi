---
UID: NC:d3dumddi.PFND3DDDI_CREATEOVERLAY
title: PFND3DDDI_CREATEOVERLAY (d3dumddi.h)
description: The CreateOverlay function allocates overlay hardware and makes the overlay visible.
old-location: display\createoverlay.htm
tech.root: display
ms.assetid: 761377ff-95a6-426b-8372-3f347870f9c4
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATEOVERLAY callback function"]
ms.keywords: CreateOverlay, CreateOverlay callback function [Display Devices], PFND3DDDI_CREATEOVERLAY, PFND3DDDI_CREATEOVERLAY callback, UserModeDisplayDriver_Functions_8418bf74-3398-4913-9002-2f0b2a0941fb.xml, d3dumddi/CreateOverlay, display.createoverlay
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
 - "d3dumddi/CreateOverlay"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateOverlay
product:
 - Windows
---

# PFND3DDDI_CREATEOVERLAY callback function

## -description

The <b>CreateOverlay</b> function allocates overlay hardware and makes the overlay visible.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createoverlay">D3DDDIARG_CREATEOVERLAY</a> structure that describes the overlay.

## -returns

<b>CreateOverlay</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The overlay is successfully created. | 
| **E_OUTOFMEMORY** | [CreateOverlay](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlay)  could not complete because of insufficient memory. | 
| **D3DDDIERR_NOTAVAILABLE** | [CreateOverlay](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createoverlay)  could not complete because insufficient bandwidth was available or the requested overlay hardware was unavailable. | 
| **D3DDDIERR_UNSUPPORTEDOVERLAYFORMAT** | The specified overlay format is not supported by the overlay hardware. | 
| **D3DDDIERR_UNSUPPORTEDOVERLAY** | The overlay hardware is not supported for the specified size and display mode. |

## -remarks

Overlays are independent from the resources that are displayed by using the overlays.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createoverlay">D3DDDIARG_CREATEOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

