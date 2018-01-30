---
UID: NE:d3d10umddi.D3D11_DDI_SHADER_MIN_PRECISION
title: D3D11_DDI_SHADER_MIN_PRECISION
author: windows-driver-content
description: Specifies minimum precision levels that the user-mode driver supports in shaders.
old-location: display\d3d11_ddi_shader_min_precision.htm
old-project: display
ms.assetid: cf77d6c7-8f42-470a-9e3a-85d95398470b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_ddi_shader_min_precision, D3D11_DDI_SHADER_MIN_PRECISION_16_BIT, D3D11_DDI_SHADER_MIN_PRECISION enumeration [Display Devices], d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION, d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION_16_BIT, D3D11_DDI_SHADER_MIN_PRECISION_10_BIT, d3d10umddi/D3D11_DDI_SHADER_MIN_PRECISION_10_BIT, D3D11_DDI_SHADER_MIN_PRECISION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_DDI_SHADER_MIN_PRECISION
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_SHADER_MIN_PRECISION
---

# D3D11_DDI_SHADER_MIN_PRECISION enumeration


## -description


Specifies minimum precision levels that the user-mode driver supports in shaders.


## -syntax


````
typedef enum D3D11_DDI_SHADER_MIN_PRECISION { 
  D3D11_DDI_SHADER_MIN_PRECISION_10_BIT  = 0x1,
  D3D11_DDI_SHADER_MIN_PRECISION_16_BIT  = 0x2
} D3D11_DDI_SHADER_MIN_PRECISION;
````


## -enum-fields




### -field D3D11_DDI_SHADER_MIN_PRECISION_10_BIT

The minimum precision level is 10-bit.


### -field D3D11_DDI_SHADER_MIN_PRECISION_16_BIT

The minimum precision level is 16-bit.

