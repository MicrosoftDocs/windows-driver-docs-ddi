---
UID: NC:d3dumddi.PFND3DDDI_SETSTREAMSOURCEUM
title: PFND3DDDI_SETSTREAMSOURCEUM (d3dumddi.h)
description: The SetStreamSourceUM function binds a vertex stream source to a user memory buffer.
old-location: display\setstreamsourceum.htm
tech.root: display
ms.assetid: 75a70801-0338-45ed-a691-5f84202575d5
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETSTREAMSOURCEUM callback function"]
ms.keywords: PFND3DDDI_SETSTREAMSOURCEUM, PFND3DDDI_SETSTREAMSOURCEUM callback, SetStreamSourceUM, SetStreamSourceUM callback function [Display Devices], UserModeDisplayDriver_Functions_0bea09c2-3bd9-4c60-9688-1c5a687e0dc9.xml, d3dumddi/SetStreamSourceUM, display.setstreamsourceum
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
 - PFND3DDDI_SETSTREAMSOURCEUM
 - d3dumddi/PFND3DDDI_SETSTREAMSOURCEUM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetStreamSourceUM
---

# PFND3DDDI_SETSTREAMSOURCEUM callback function


## -description

The <i>SetStreamSourceUM</i> function binds a vertex stream source to a user memory buffer.

## -parameters

### -param hDevice 

[in]
A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setstreamsourceum">D3DDDIARG_SETSTREAMSOURCEUM</a> structure that specifies the vertex stream source to bind.

### -param Arg3

*pUMBuffer* [in]

A pointer to the user-memory buffer that supplies the vertex data for the vertex stream source.

## -returns

<i>SetStreamSourceUM</i> returns S_OK or an appropriate error result if the vertex stream source is not successfully bound.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_setstreamsourceum">D3DDDIARG_SETSTREAMSOURCEUM</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>