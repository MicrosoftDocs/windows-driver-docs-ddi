---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT
title: PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT (d3d10umddi.h)
description: Queries the number of video decoder profiles that are supported by the display miniport driver.
old-location: display\getvideodecoderprofilecount.htm
ms.assetid: ae24bc29-177e-48a1-adf9-ed8c79b7f39c
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT, PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT callback, d3d10umddi/pfnGetVideoDecoderProfileCount, display.getvideodecoderprofilecount, pfnGetVideoDecoderProfileCount, pfnGetVideoDecoderProfileCount callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT
 - d3d10umddi/PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetVideoDecoderProfileCount
product:
 - Windows
---

# PFND3D11_1DDI_GETVIDEODECODERPROFILECOUNT callback function


## -description

Queries the number of video decoder profiles that are supported by the display miniport driver.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pDecodeProfileCount* [out]

A pointer to a UINT value that specifies the maximum number of decoder profiles that are supported.

