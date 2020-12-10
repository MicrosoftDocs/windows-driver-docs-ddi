---
UID: NC:d3dumddi.PFND3DDDI_PRESENT1
title: PFND3DDDI_PRESENT1 (d3dumddi.h)
description: Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.
old-location: display\pfnpresent1_d3d_.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_PRESENT1 callback function"]
ms.keywords: PFND3DDDI_PRESENT1, PFND3DDDI_PRESENT1 callback, d3dumddi/pfnPresent1, display.pfnpresent1_d3d_, pfnPresent1, pfnPresent1 callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFND3DDDI_PRESENT1
 - d3dumddi/PFND3DDDI_PRESENT1
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dumddi.h
api_name:
 - pfnPresent1
product:
 - Windows
---

# PFND3DDDI_PRESENT1 callback function


## -description

Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pPresentData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_present1">D3DDDIARG_PRESENT1</a> structure that describes how to display to the destination surface.

## -returns

Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.

## -remarks

The user-mode display driver must submit all partially built render data (command buffers) by calling the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>  function. The driver must make only  a single call to <b>pfnRenderCb</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_present1">D3DDDIARG_PRESENT1</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_rendercb">pfnRenderCb</a>
