---
UID: NC:d3dumddi.PFND3DDDI_CAPTURETOSYSMEM
title: PFND3DDDI_CAPTURETOSYSMEM (d3dumddi.h)
description: The CaptureToSysMem function copies the contents of a capture buffer to a destination surface.
old-location: display\capturetosysmem.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CAPTURETOSYSMEM callback function"]
ms.keywords: CaptureToSysMem, CaptureToSysMem callback function [Display Devices], PFND3DDDI_CAPTURETOSYSMEM, PFND3DDDI_CAPTURETOSYSMEM callback, UserModeDisplayDriver_Functions_9d7270cc-da5e-4c04-8ab6-93b9cfd7a475.xml, d3dumddi/CaptureToSysMem, display.capturetosysmem
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
 - PFND3DDDI_CAPTURETOSYSMEM
 - d3dumddi/PFND3DDDI_CAPTURETOSYSMEM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CaptureToSysMem
product:
 - Windows
---

# PFND3DDDI_CAPTURETOSYSMEM callback function


## -description

The <b>CaptureToSysMem</b> function copies the contents of a capture buffer to a destination surface.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

pData [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_capturetosysmem">D3DDDIARG_CAPTURETOSYSMEM</a> structure that describes the parameters of the bit-block transfer (bitblt).

## -returns

<b>CaptureToSysMem</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | All resources for the bitblt are in GPU-accessible memory. | 
| **E_OUTOFMEMORY** | [CaptureToSysMem]()  could not allocate the required memory for it to complete. |

## -remarks

The <b>CaptureToSysMem</b> function is similar to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_blt">Blt</a> function except that <b>CaptureToSysMem</b> supports copying only from a capture buffer.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_capturetosysmem">D3DDDIARG_CAPTURETOSYSMEM</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
