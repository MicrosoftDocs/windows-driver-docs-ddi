---
UID: NS:d3d12umddi.D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
title: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
author: windows-driver-content
description: Specifies texture layout capabilities.
old-location: display\d3d12ddi_texture_layout_caps_0001.htm
old-project: display
ms.assetid: CFA0C474-129A-4A05-B426-520B96C318D8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 structure [Display Devices], display.d3d12ddi_texture_layout_caps_0001, d3d12umddi/D3D12DDI_TEXTURE_LAYOUT_CAPS_0001, D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
product: Windows
targetos: Windows
req.typenames: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
---

# D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 structure


## -description


Specifies texture layout capabilities.


## -syntax


````
typedef struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 {
  UINT DeviceDependentLayoutCount;
  UINT DeviceDependentSwizzleCount;
  BOOL Supports64KStandardSwizzle;
} D3D12DDI_TEXTURE_LAYOUT_CAPS_0001;
````


## -struct-fields




### -field DeviceDependentLayoutCount

A device dependent layout count. This must be the number of device-dependent layouts supported by the adapter. 


### -field DeviceDependentSwizzleCount

A device dependent swizzle count. This must be the number of device-dependent swizzle patterns supported by the adapter. 


### -field Supports64KStandardSwizzle

Whether the texture layout supports 64K standard swizzle.


### -field SupportsRowMajorTexture

 



