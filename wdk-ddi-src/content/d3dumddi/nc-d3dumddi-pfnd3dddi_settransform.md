---
UID: NC:d3dumddi.PFND3DDDI_SETTRANSFORM
title: PFND3DDDI_SETTRANSFORM (d3dumddi.h)
description: The SetTransform function sets up a transform.
old-location: display\settransform.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETTRANSFORM callback function"]
ms.keywords: PFND3DDDI_SETTRANSFORM, PFND3DDDI_SETTRANSFORM callback, SetTransform, SetTransform callback function [Display Devices], UserModeDisplayDriver_Functions_721be745-bcea-4eeb-9bd4-ddda1f1912a5.xml, d3dumddi/SetTransform, display.settransform
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
 - PFND3DDDI_SETTRANSFORM
 - d3dumddi/PFND3DDDI_SETTRANSFORM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetTransform
product:
 - Windows
---

# PFND3DDDI_SETTRANSFORM callback function


## -description

The <i>SetTransform</i> function sets up a transform.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_settransform">D3DDDIARG_SETTRANSFORM</a> structure that describes how to set up the transform.

## -returns

<i>SetTransform</i> returns S_OK or an appropriate error result if the transform is not successfully set up.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_settransform">D3DDDIARG_SETTRANSFORM</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
