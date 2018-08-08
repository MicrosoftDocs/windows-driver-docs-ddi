---
UID: NS:d3d10umddi.D3DWDDM2_4DDI_VIDEO_INPUT
title: D3DWDDM2_4DDI_VIDEO_INPUT
author: windows-driver-content
description:
ms.assetid: 5e4a2b72-95ef-4a69-811d-128645c7bf67
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3DWDDM2_4DDI_VIDEO_INPUT, D3DWDDM2_4DDI_VIDEO_INPUT,
req.header: d3d10umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3DWDDM2_4DDI_VIDEO_INPUT
topictype:
-	apiref
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3DWDDM2_4DDI_VIDEO_INPUT
product: 
- Windows
targetos: Windows
---

# D3DWDDM2_4DDI_VIDEO_INPUT structure

## -description

D3DWDDM2_4DDI_VIDEO_INPUT contains the JPEG image function table that is provided to the Microsoft DirectX graphics kernel by the user mode driver.

## -struct-fields

### -field Relocate

Indicates that the functions can be relocated.

### -field pWDDM2_4VideoDeviceFuncs

A pointer to a D3DWDDM2_4DDI_VIDEODEVICEFUNCS structure that contains the image function pointers.

## -remarks

## -see-also

[D3DWDDM2_4DDI_VIDEODEVICEFUNCS](ns-d3d10umddi-d3dwddm2_4ddi_videodevicefuncs.md)