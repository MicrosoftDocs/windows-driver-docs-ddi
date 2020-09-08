---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
title: PFND3DWDDM2_0DDI_GETRESOURCELAYOUT (d3d10umddi.h)
description: The pfnGetResourceLayout callback function supports getting resource layout information.
old-location: display\pfnd3dwddm2_0ddi_getresourcelayout.htm
ms.assetid: 0158F1B4-AA6E-41F9-BAEF-A3C688758205
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_0DDI_GETRESOURCELAYOUT callback function"]
ms.keywords: PFND3DWDDM2_0DDI_GETRESOURCELAYOUT, PFND3DWDDM2_0DDI_GETRESOURCELAYOUT callback, d3d10umddi/pfnGetResourceLayout, display.pfnd3dwddm2_0ddi_getresourcelayout, pfnGetResourceLayout, pfnGetResourceLayout callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
 - d3d10umddi/PFND3DWDDM2_0DDI_GETRESOURCELAYOUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnGetResourceLayout
---

# PFND3DWDDM2_0DDI_GETRESOURCELAYOUT callback function


## -description

The <i>pfnGetResourceLayout</i> callback function supports getting resource layout information.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource*

A resource handle.

### -param SubresourceCount

The subresource count.

### -param Arg4

*Handle* [out]

A kernel handle.

### -param Arg5

*TextureLayout* [out]

A pointer to a texture layout.

### -param pMipLevelSwizzleTransition 

[out]
A pointer to a MIP level swizzle transition.

### -param Arg7

*SubresourceLayout* [out, optional]

A pointer to the subresource layout.

