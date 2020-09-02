---
UID: NC:d3dumddi.PFND3DDDI_DESTROYOVERLAY
title: PFND3DDDI_DESTROYOVERLAY (d3dumddi.h)
description: The DestroyOverlay function disables the overlay hardware and frees the overlay handle.
old-location: display\destroyoverlay.htm
tech.root: display
ms.assetid: 63004d19-e2cd-462c-8fa5-ea4dd6e29735
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DESTROYOVERLAY callback function"]
ms.keywords: DestroyOverlay, DestroyOverlay callback function [Display Devices], PFND3DDDI_DESTROYOVERLAY, PFND3DDDI_DESTROYOVERLAY callback, UserModeDisplayDriver_Functions_e3dd8286-aff0-40c0-8cf2-84ecc706df90.xml, d3dumddi/DestroyOverlay, display.destroyoverlay
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
 - PFND3DDDI_DESTROYOVERLAY
 - d3dumddi/PFND3DDDI_DESTROYOVERLAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DestroyOverlay
product:
 - Windows
---

# PFND3DDDI_DESTROYOVERLAY callback function


## -description

The <b>DestroyOverlay</b> function disables the overlay hardware and frees the overlay handle.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_destroyoverlay">D3DDDIARG_DESTROYOVERLAY</a> structure that contains the overlay handle.

## -returns

<b>DestroyOverlay</b> returns S_OK or an appropriate error result if the overlay hardware is not disabled.

## -remarks

Overlays are independent from the resources that are displayed by using the overlays.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_destroyoverlay">D3DDDIARG_DESTROYOVERLAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

