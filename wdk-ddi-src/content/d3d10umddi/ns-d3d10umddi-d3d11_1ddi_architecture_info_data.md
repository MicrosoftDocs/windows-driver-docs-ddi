---
UID: NS:d3d10umddi.D3D11_1DDI_ARCHITECTURE_INFO_DATA
title: D3D11_1DDI_ARCHITECTURE_INFO_DATA (d3d10umddi.h)
description: Describes information about display adapter architecture.
old-location: display\d3d11_1ddi_architecture_info_data.htm
ms.assetid: 262d511d-2846-415d-b1b8-2687f12f9f78
ms.date: 05/10/2018
ms.keywords: D3D11_1DDI_ARCHITECTURE_INFO_DATA, D3D11_1DDI_ARCHITECTURE_INFO_DATA structure [Display Devices], d3d10umddi/D3D11_1DDI_ARCHITECTURE_INFO_DATA, display.d3d11_1ddi_architecture_info_data
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_ARCHITECTURE_INFO_DATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d10umddi.h
api_name:
- D3D11_1DDI_ARCHITECTURE_INFO_DATA
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_ARCHITECTURE_INFO_DATA
---

# D3D11_1DDI_ARCHITECTURE_INFO_DATA structure


## -description


Describes information about display adapter architecture.


## -struct-fields




### -field TileBasedDeferredRenderer

Specifies whether a rendering device batches rendering commands and performs multipass rendering into tiles or bins over a render area. The value is <b>TRUE</b> if the rendering device batches rendering commands and <b>FALSE</b> otherwise.

