---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEODECODER_0021
title: PFND3D12DDI_CREATEVIDEODECODER_0021 (d3d12umddi.h)
description: The pfnCreateVideoDecoder callback function creates a video decoder.
old-location: display\pfnd3d12ddi_createvideodecoder.htm
ms.assetid: 5E0B6A5A-FA6E-4722-B442-FE74437224B3
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CREATEVIDEODECODER_0021, PFND3D12DDI_CREATEVIDEODECODER_0021 callback, d3d12umddi/pfnCreateVideoDecoder, display.pfnd3d12ddi_createvideodecoder, pfnCreateVideoDecoder, pfnCreateVideoDecoder callback function [Display Devices]
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnCreateVideoDecoder
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATEVIDEODECODER_0021 callback function


## -description


The <i>pfnCreateVideoDecoder</i> callback function creates a video decoder.


## -parameters




### -param hDrvDevice

The hardware device being processed.

### -param *pArgs

*CreateVideoDecoder* [in]

The arguments used to create a video decoder.

### -param hDrvVideoDecoder

The handle of a driver video decoder.





## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



