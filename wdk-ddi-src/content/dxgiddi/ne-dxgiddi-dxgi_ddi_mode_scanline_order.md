---
UID: NE:dxgiddi.DXGI_DDI_MODE_SCANLINE_ORDER
title: DXGI_DDI_MODE_SCANLINE_ORDER (dxgiddi.h)
description: The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.
old-location: display\dxgi_ddi_mode_scanline_order.htm
tech.root: display
ms.assetid: 114a6f0d-22ec-4306-81b4-56cf882f167f
ms.date: 05/10/2018
ms.keywords: DXGI_DDI_MODE_SCANLINE_ORDER, DXGI_DDI_MODE_SCANLINE_ORDER enumeration [Display Devices], DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST, DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE, DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED, DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST, UMDisplayDriver_Dx10param_Structs_fe7ff8f4-48e3-4ec5-a401-35d729a17440.xml, display.dxgi_ddi_mode_scanline_order, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED, dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST
ms.topic: enum
f1_keywords:
 - "dxgiddi/DXGI_DDI_MODE_SCANLINE_ORDER"
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxgiddi.h
api_name:
- DXGI_DDI_MODE_SCANLINE_ORDER
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_MODE_SCANLINE_ORDER
---

# DXGI_DDI_MODE_SCANLINE_ORDER enumeration


## -description


The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.


## -enum-fields




### -field DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED

A DXGI_DDI_MODE_SCANLINE_ORDER-typed variable has not yet been assigned a meaningful value.


### -field DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE

Each field contains an entire frame.


### -field DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST

Each field contains half of a frame, and the odd scan lines are displayed first.


### -field DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST

Each field contains half of a frame, and the even scan lines are displayed first.


## -remarks



The values of the DXGI_DDI_MODE_SCANLINE_ORDER enumeration type indicate whether the image that is displayed on the monitor contains the entire content of a video frame or only half of the content (that is, either the even or odd scan lines, which occur interchangeably). The values also indicate which field comes first in the order.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi_ddi_mode_desc">DXGI_DDI_MODE_DESC</a>
 

 

