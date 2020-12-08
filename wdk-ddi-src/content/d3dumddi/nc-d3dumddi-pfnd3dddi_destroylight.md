---
UID: NC:d3dumddi.PFND3DDDI_DESTROYLIGHT
title: PFND3DDDI_DESTROYLIGHT (d3dumddi.h)
description: The DestroyLight function deactivates a light source.
old-location: display\destroylight.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DESTROYLIGHT callback function"]
ms.keywords: DestroyLight, DestroyLight callback function [Display Devices], PFND3DDDI_DESTROYLIGHT, PFND3DDDI_DESTROYLIGHT callback, UserModeDisplayDriver_Functions_fce83d93-bfe6-44f9-a1c4-ea92921bfb69.xml, d3dumddi/DestroyLight, display.destroylight
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
 - PFND3DDDI_DESTROYLIGHT
 - d3dumddi/PFND3DDDI_DESTROYLIGHT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DestroyLight
product:
 - Windows
---

# PFND3DDDI_DESTROYLIGHT callback function


## -description

The <b>DestroyLight</b> function deactivates a light source.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_destroylight">D3DDDIARG_DESTROYLIGHT</a> structure that describes how to set the light source.

## -returns

<b>DestroyLight</b> returns S_OK or an appropriate error result if the light source is not successfully deactivated.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_destroylight">D3DDDIARG_DESTROYLIGHT</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
