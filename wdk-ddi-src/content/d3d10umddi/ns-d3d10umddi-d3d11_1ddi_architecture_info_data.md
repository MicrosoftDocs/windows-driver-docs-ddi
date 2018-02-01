---
UID: NS:d3d10umddi.D3D11_1DDI_ARCHITECTURE_INFO_DATA
title: D3D11_1DDI_ARCHITECTURE_INFO_DATA
author: windows-driver-content
description: Describes information about display adapter architecture.
old-location: display\d3d11_1ddi_architecture_info_data.htm
old-project: display
ms.assetid: 262d511d-2846-415d-b1b8-2687f12f9f78
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_ARCHITECTURE_INFO_DATA, D3D11_1DDI_ARCHITECTURE_INFO_DATA, display.d3d11_1ddi_architecture_info_data, D3D11_1DDI_ARCHITECTURE_INFO_DATA structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	d3d10umddi.h
apiname:
-	D3D11_1DDI_ARCHITECTURE_INFO_DATA
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_ARCHITECTURE_INFO_DATA
---

# D3D11_1DDI_ARCHITECTURE_INFO_DATA structure


## -description


Describes information about display adapter architecture.


## -syntax


````
typedef struct D3D11_1DDI_ARCHITECTURE_INFO_DATA {
  BOOL TileBasedDeferredRenderer;
} D3D11_1DDI_ARCHITECTURE_INFO_DATA;
````


## -struct-fields




### -field TileBasedDeferredRenderer

Specifies whether a rendering device batches rendering commands and performs multipass rendering into tiles or bins over a render area. The value is <b>TRUE</b> if the rendering device batches rendering commands and <b>FALSE</b> otherwise.

