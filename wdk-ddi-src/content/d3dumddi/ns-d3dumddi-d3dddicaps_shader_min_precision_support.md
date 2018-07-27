---
UID: NS:d3dumddi.D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
title: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
author: windows-driver-content
description: Describes precision support options for shaders in the user-mode display driver.
old-location: display\d3dddicaps_shader_min_precision_support.htm
tech.root: display
ms.assetid: c3ad65e7-8a91-464b-9a7f-e5c47ee54048
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT, D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT structure [Display Devices], d3dumddi/D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT, display.d3dddicaps_shader_min_precision_support
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT
---

# D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT structure


## -description


Describes precision support options for shaders in the user-mode display driver.


## -struct-fields




### -field VertexShaderMinPrecision

A combination of values of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh451152">D3DDDICAPS_SHADER_MIN_PRECISION</a> that are combined by using a bitwise OR operation. The resulting value specifies minimum precision levels that the driver supports for the vertex shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


### -field PixelShaderMinPrecision

A combination of values of type <a href="https://msdn.microsoft.com/library/windows/hardware/hh451152">D3DDDICAPS_SHADER_MIN_PRECISION</a> that are combined by using a bitwise OR operation. The resulting value specifies minimum precision levels that the driver supports for the pixel shader. A value of zero indicates that the driver supports only the default precision for the shader model, and not a lower precision.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451152">D3DDDICAPS_SHADER_MIN_PRECISION</a>
 

 

