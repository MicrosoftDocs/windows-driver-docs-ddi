---
UID: NE:d3d12umddi.D3D12DDI_CREATE_SHADER_FLAGS
title: D3D12DDI_CREATE_SHADER_FLAGS
author: windows-driver-content
description: Defines flags for shader creation.
old-location: display\d3d12ddi_create_shader_flags.htm
old-project: display
ms.assetid: 93F27775-3E74-4310-8E09-DCB079436706
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: d3d12umddi/D3D12DDI_CREATE_SHADER_FLAGS, D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING, D3D12DDI_CREATE_SHADER_FLAGS, display.d3d12ddi_create_shader_flags, D3D12DDI_CREATE_SHADER_FLAG_NONE, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_NONE, D3D12DDI_CREATE_SHADER_FLAGS enumeration [Display Devices], D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING, d3d12umddi/D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_CREATE_SHADER_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_CREATE_SHADER_FLAGS
---

# D3D12DDI_CREATE_SHADER_FLAGS enumeration


## -description


Defines flags for shader creation.


## -syntax


````
typedef enum D3D12DDI_CREATE_SHADER_FLAGS { 
  D3D12DDI_CREATE_SHADER_FLAG_NONE                   = 0x0,
  D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING  = 0x1,
  D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION   = 0x2
} D3D12DDI_CREATE_SHADER_FLAGS;
````


## -enum-fields




### -field D3D12DDI_CREATE_SHADER_FLAG_NONE

No flag value for shader creation.


### -field D3D12DDI_CREATE_SHADER_FLAG_ENABLE_SHADER_TRACING

The shader is tracing. 


### -field D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION_0024




#### - D3D12DDI_CREATE_SHADER_FLAG_DISABLE_OPTIMIZATION

The shader is compiled quickly and less optimally. 

