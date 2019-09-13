---
UID: NC:d3dumddi.PFND3DDDI_SETTEXTURE
title: PFND3DDDI_SETTEXTURE (d3dumddi.h)
description: The SetTexture function inserts a texture at a particular stage in a multiple-texture group.
old-location: display\settexture.htm
tech.root: display
ms.assetid: b2ed86c5-cd4f-4aaa-a062-4c7ae4e088df
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETTEXTURE, PFND3DDDI_SETTEXTURE callback, SetTexture, SetTexture callback function [Display Devices], UserModeDisplayDriver_Functions_f85a8797-cbcc-40df-a339-af69ce128e95.xml, d3dumddi/SetTexture, display.settexture
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
 - "d3dumddi/SetTexture"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetTexture
product:
 - Windows
---

# PFND3DDDI_SETTEXTURE callback function

## -description

The <i>SetTexture</i> function inserts a texture at a particular stage in a multiple-texture group.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*hTexture* [in]

A handle to the texture to insert.

### -param Arg3

## -returns

<i>SetTexture</i> returns S_OK or an appropriate error result if the texture is not successfully inserted.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

