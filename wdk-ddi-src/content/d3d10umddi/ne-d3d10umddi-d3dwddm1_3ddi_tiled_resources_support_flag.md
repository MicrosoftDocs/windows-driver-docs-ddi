---
UID: NE:d3d10umddi.D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
title: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
author: windows-driver-content
description: Indicates the level of support by the hardware and user-mode display driver for tiled resources.
old-location: display\d3dwddm1_3ddi_tiled_resources_support_flag.htm
old-project: display
ms.assetid: 5EEF8C68-0DE7-466B-946F-37157B21C9B7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG, D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration [Display Devices], D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED, D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED, d3d10umddi/D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG, d3d10umddi/D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED, d3d10umddi/D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED, display.d3dwddm1_3ddi_tiled_resources_support_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3d10umddi.h
api_name:
-	D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
---

# D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration


## -description


Indicates the level of support by the hardware and user-mode display driver for tiled resources.


## -syntax


````
typedef enum _D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG { 
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED  = 0x00000001,
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED  = 0x00000002
} D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG;
````


## -enum-fields




### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED

Tiled resources are supported to a  minimal level.


### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED

Tiled resources are supported to a greater extent than for <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b>.

If this flag is set, the Direct3D runtime assumes that the support level of the <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b> flag also applies.


### -field D3DWDDM2_0DDI_TILED_RESOURCES_TIER_3_SUPPORTED




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1.md">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a>



 

 


