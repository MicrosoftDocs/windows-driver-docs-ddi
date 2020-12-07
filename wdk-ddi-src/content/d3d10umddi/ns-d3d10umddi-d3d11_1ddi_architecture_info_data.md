---
UID: NS:d3d10umddi.D3D11_1DDI_ARCHITECTURE_INFO_DATA
title: D3D11_1DDI_ARCHITECTURE_INFO_DATA (d3d10umddi.h)
description: Describes information about display adapter architecture.
old-location: display\d3d11_1ddi_architecture_info_data.htm
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_ARCHITECTURE_INFO_DATA structure"]
ms.keywords: D3D11_1DDI_ARCHITECTURE_INFO_DATA, D3D11_1DDI_ARCHITECTURE_INFO_DATA structure [Display Devices], d3d10umddi/D3D11_1DDI_ARCHITECTURE_INFO_DATA, display.d3d11_1ddi_architecture_info_data
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_ARCHITECTURE_INFO_DATA
f1_keywords:
 - D3D11_1DDI_ARCHITECTURE_INFO_DATA
 - d3d10umddi/D3D11_1DDI_ARCHITECTURE_INFO_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D11_1DDI_ARCHITECTURE_INFO_DATA
---

# D3D11_1DDI_ARCHITECTURE_INFO_DATA structure


## -description

Describes information about display adapter architecture.

## -struct-fields

### -field TileBasedDeferredRenderer

Specifies whether a rendering device batches rendering commands and performs multipass rendering into tiles or bins over a render area. The value is <b>TRUE</b> if the rendering device batches rendering commands and <b>FALSE</b> otherwise.

