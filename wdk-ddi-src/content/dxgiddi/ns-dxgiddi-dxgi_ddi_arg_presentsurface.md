---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENTSURFACE
title: DXGI_DDI_ARG_PRESENTSURFACE (dxgiddi.h)
description: Describes a surface to display.
old-location: display\dxgi_ddi_arg_presentsurface.htm
tech.root: display
ms.assetid: 1A1E2644-7411-4D69-8D45-B19D707221AB
ms.date: 05/10/2018
keywords: ["DXGI_DDI_ARG_PRESENTSURFACE structure"]
ms.keywords: DXGI_DDI_ARG_PRESENTSURFACE, DXGI_DDI_ARG_PRESENTSURFACE structure [Display Devices], display.dxgi_ddi_arg_presentsurface, dxgiddi/DXGI_DDI_ARG_PRESENTSURFACE
f1_keywords:
 - "dxgiddi/DXGI_DDI_ARG_PRESENTSURFACE"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dxgiddi.h
api_name:
- DXGI_DDI_ARG_PRESENTSURFACE
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_PRESENTSURFACE
---

# DXGI_DDI_ARG_PRESENTSURFACE structure


## -description


Describes a surface to display.


## -struct-fields




### -field hSurface

[in] A handle to the resource that contains the surface. 


### -field SubResourceIndex

The zero-based index into the resource, which the handle in the <b>hSurface</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface.

