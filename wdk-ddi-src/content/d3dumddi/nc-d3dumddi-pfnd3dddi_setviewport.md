---
UID: NC:d3dumddi.PFND3DDDI_SETVIEWPORT
title: PFND3DDDI_SETVIEWPORT (d3dumddi.h)
description: The SetViewport function informs guard-band-aware drivers of the view-clipping rectangle.
old-location: display\setviewport.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETVIEWPORT callback function"]
ms.keywords: PFND3DDDI_SETVIEWPORT, PFND3DDDI_SETVIEWPORT callback, SetViewport, SetViewport callback function [Display Devices], UserModeDisplayDriver_Functions_6b0d00a2-6316-4ac0-878c-e8554e92ef57.xml, d3dumddi/SetViewport, display.setviewport
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
 - PFND3DDDI_SETVIEWPORT
 - d3dumddi/PFND3DDDI_SETVIEWPORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_SETVIEWPORT
---

# PFND3DDDI_SETVIEWPORT callback function


## -description

The <i>SetViewport</i> function informs guard-band-aware drivers of the view-clipping rectangle.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param unnamedParam2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_viewportinfo">D3DDDIARG_VIEWPORTINFO</a> structure that describes the view-clipping rectangle.

## -returns

<i>SetViewport</i> returns S_OK or an appropriate error result if the driver is not successfully informed about the view-clipping rectangle.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_viewportinfo">D3DDDIARG_VIEWPORTINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

