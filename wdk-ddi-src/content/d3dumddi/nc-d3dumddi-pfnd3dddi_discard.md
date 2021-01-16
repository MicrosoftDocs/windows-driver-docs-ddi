---
UID: NC:d3dumddi.PFND3DDDI_DISCARD
title: PFND3DDDI_DISCARD (d3dumddi.h)
description: Discards (evicts) a set of subresources from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\discard.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DISCARD callback function"]
ms.keywords: Discard, Discard callback function [Display Devices], PFND3DDDI_DISCARD, PFND3DDDI_DISCARD callback, d3dumddi/Discard, display.discard
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - PFND3DDDI_DISCARD
 - d3dumddi/PFND3DDDI_DISCARD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_DISCARD
product:
 - Windows
---

# PFND3DDDI_DISCARD callback function


## -description

Discards (evicts) a set of subresources from video display memory. Implemented by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_discard">D3DDDIARG_DISCARD</a> structure that defines the set of subresources that is to be discarded.

## -returns

       Returns S_OK if successful, or an appropriate error result if the operation is not successful.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_discard">D3DDDIARG_DISCARD</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

