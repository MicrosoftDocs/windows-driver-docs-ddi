---
UID: NC:d3dumddi.PFND3DDDI_STATESET
title: PFND3DDDI_STATESET (d3dumddi.h)
description: The StateSet function sets a state block.
old-location: display\stateset.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_STATESET callback function"]
ms.keywords: PFND3DDDI_STATESET, PFND3DDDI_STATESET callback, StateSet, StateSet callback function [Display Devices], UserModeDisplayDriver_Functions_ca9843ce-a32d-4d81-844a-213b7fe6c6e0.xml, d3dumddi/StateSet, display.stateset
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
 - PFND3DDDI_STATESET
 - d3dumddi/PFND3DDDI_STATESET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_STATESET
product:
 - Windows
---

# PFND3DDDI_STATESET callback function


## -description

The <i>StateSet</i> function sets a state block.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_stateset">D3DDDIARG_STATESET</a> structure that describes how to set the state block.

## -returns

<i>StateSet</i> returns S_OK or an appropriate error result if the state block is not successfully set.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_stateset">D3DDDIARG_STATESET</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

