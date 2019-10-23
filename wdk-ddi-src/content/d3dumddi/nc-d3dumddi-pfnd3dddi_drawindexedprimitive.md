---
UID: NC:d3dumddi.PFND3DDDI_DRAWINDEXEDPRIMITIVE
title: PFND3DDDI_DRAWINDEXEDPRIMITIVE (d3dumddi.h)
description: The DrawIndexedPrimitive function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.
old-location: display\drawindexedprimitive.htm
tech.root: display
ms.assetid: 12bb6274-d042-43bb-b9f5-1417f42da729
ms.date: 05/10/2018
ms.keywords: DrawIndexedPrimitive, DrawIndexedPrimitive callback function [Display Devices], PFND3DDDI_DRAWINDEXEDPRIMITIVE, PFND3DDDI_DRAWINDEXEDPRIMITIVE callback, UserModeDisplayDriver_Functions_427fa7b5-5b52-4314-b097-aea6d27cb535.xml, d3dumddi/DrawIndexedPrimitive, display.drawindexedprimitive
ms.topic: callback
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
 - "d3dumddi/DrawIndexedPrimitive"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DrawIndexedPrimitive
product:
 - Windows
---

# PFND3DDDI_DRAWINDEXEDPRIMITIVE callback function

## -description

The <b>DrawIndexedPrimitive</b> function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawindexedprimitive">D3DDDIARG_DRAWINDEXEDPRIMITIVE</a> structure that describes the indexed primitive to draw.

## -returns

<b>DrawIndexedPrimitive</b> returns S_OK or an appropriate error result if the indexed primitive is not successfully drawn.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_drawindexedprimitive">D3DDDIARG_DRAWINDEXEDPRIMITIVE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_drawindexedprimitive2">DrawIndexedPrimitive2</a>

