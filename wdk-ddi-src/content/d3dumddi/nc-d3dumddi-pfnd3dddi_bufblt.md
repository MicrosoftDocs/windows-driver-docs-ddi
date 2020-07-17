---
UID: NC:d3dumddi.PFND3DDDI_BUFBLT
title: PFND3DDDI_BUFBLT (d3dumddi.h)
description: The BufBlt function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.
old-location: display\bufblt.htm
tech.root: display
ms.assetid: d75f3fad-3bcd-44ad-9bd5-f61f5346cf8d
ms.date: 05/10/2018
keywords: ["PFND3DDDI_BUFBLT callback function"]
ms.keywords: BufBlt, BufBlt callback function [Display Devices], PFND3DDDI_BUFBLT, PFND3DDDI_BUFBLT callback, UserModeDisplayDriver_Functions_87f3469d-cae9-43e7-a0ae-d19bef34314e.xml, d3dumddi/BufBlt, display.bufblt
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
 - "d3dumddi/BufBlt"
 - "BufBlt"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - BufBlt
product:
 - Windows
---

# PFND3DDDI_BUFBLT callback function

## -description

The <b>BufBlt</b> function performs a bit-block transfer (bitblt) operation from a source vertex or index buffer to a destination vertex or index buffer.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_bufferblt">D3DDDIARG_BUFFERBLT</a> structure that describes the parameters of the buffer bitblt operation.

## -returns

<b>BufBlt</b> returns S_OK or an appropriate error result if the buffer bitblt operation is not successfully performed.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_bufferblt">D3DDDIARG_BUFFERBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

