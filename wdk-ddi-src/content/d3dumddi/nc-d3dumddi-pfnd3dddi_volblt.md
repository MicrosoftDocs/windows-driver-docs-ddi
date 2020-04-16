---
UID: NC:d3dumddi.PFND3DDDI_VOLBLT
title: PFND3DDDI_VOLBLT (d3dumddi.h)
description: The VolBlt function performs a bit-block transfer (bitblt) operation from a source volume texture to a destination volume texture.
old-location: display\volblt.htm
tech.root: display
ms.assetid: 249a55a3-f2cf-4838-8a0f-b7108a17cd78
ms.date: 05/10/2018
keywords: ["PFND3DDDI_VOLBLT callback function"]
ms.keywords: PFND3DDDI_VOLBLT, PFND3DDDI_VOLBLT callback, UserModeDisplayDriver_Functions_2e451776-9da9-48d0-b766-979f361b96eb.xml, VolBlt, VolBlt callback function [Display Devices], d3dumddi/VolBlt, display.volblt
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
 - "d3dumddi/VolBlt"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - VolBlt
product:
 - Windows
---

# PFND3DDDI_VOLBLT callback function

## -description

The <i>VolBlt</i> function performs a bit-block transfer (bitblt) operation from a source volume texture to a destination volume texture.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_volumeblt">D3DDDIARG_VOLUMEBLT</a> structure that defines the parameters for the volume bitblt operation.

## -returns

<i>VolBlt</i> returns S_OK or an appropriate error result if the volume bitblt operation is not successfully performed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_volumeblt">D3DDDIARG_VOLUMEBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

