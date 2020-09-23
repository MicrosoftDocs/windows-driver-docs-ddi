---
UID: NC:d3dumddi.PFND3DDDI_SETZRANGE
title: PFND3DDDI_SETZRANGE (d3dumddi.h)
description: The SetZRange function informs the driver about the range of z values.
old-location: display\setzrange.htm
tech.root: display
ms.assetid: 29ccde7c-801c-4e90-bc39-8581f262cc65
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETZRANGE callback function"]
ms.keywords: PFND3DDDI_SETZRANGE, PFND3DDDI_SETZRANGE callback, SetZRange, SetZRange callback function [Display Devices], UserModeDisplayDriver_Functions_1f472784-89a0-4ddf-ae47-ee891774d03e.xml, d3dumddi/SetZRange, display.setzrange
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
 - PFND3DDDI_SETZRANGE
 - d3dumddi/PFND3DDDI_SETZRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetZRange
product:
 - Windows
---

# PFND3DDDI_SETZRANGE callback function


## -description

The <i>SetZRange</i> function informs the driver about the range of z values.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_zrange">D3DDDIARG_ZRANGE</a> structure that specifies minimum and maximum values for the range of z values.

## -returns

<i>SetZRange</i> returns S_OK or an appropriate error result if the driver is not successfully informed about the range of z values.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_zrange">D3DDDIARG_ZRANGE</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>