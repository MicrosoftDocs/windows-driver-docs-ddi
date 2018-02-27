---
UID: NS:d3d10umddi.D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
title: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
author: windows-driver-content
description: Specifies the level of support by the hardware and user-mode display driver for tiled resources.
old-location: display\d3dwddm1_3ddi_d3d11_options_data1.htm
old-project: display
ms.assetid: 822819CE-DF40-4AFD-966A-DA5C433646D7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1, D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 structure [Display Devices], d3d10umddi/D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1, display.d3dwddm1_3ddi_d3d11_options_data1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
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
-	d3d10umddi.h
api_name:
-	D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
---

# D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 structure


## -description


Specifies the level of support by the hardware and user-mode display driver for tiled resources.


## -syntax


````
typedef struct _D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 {
  UINT TiledResourcesSupportFlags;
} D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1;
````


## -struct-fields




### -field TiledResourcesSupportFlags

A value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tiled_resources_support_flag.md">D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG</a> enumeration that indicates the level of support  for tiled resources.


## -see-also

<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tiled_resources_support_flag.md">D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

