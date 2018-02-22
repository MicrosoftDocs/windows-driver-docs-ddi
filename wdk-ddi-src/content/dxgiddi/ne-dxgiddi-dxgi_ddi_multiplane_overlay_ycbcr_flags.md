---
UID: NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title: DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
author: windows-driver-content
description: Identifies YUV range and conversion info that describes a multiplane overlay.
old-location: display\dxgi_ddi_multiplane_overlay_ycbcr_flags.htm
old-project: display
ms.assetid: fa915ec0-167f-441c-b2de-0ae2b852c432
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration [Display Devices], dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, display.dxgi_ddi_multiplane_overlay_ycbcr_flags, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dxgiddi.h
apiname:
-	DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration


## -description


Identifies YUV range and conversion info that describes a multiplane overlay.


## -syntax


````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS { 
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE  = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709          = 0x2,
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC          = 0x4
} DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS;
````


## -enum-fields




### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE

YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709

YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.


### -field DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC

YUV values contain xvYCC data, instead of conventional YCbCr data.


## -remarks



For more info on how YUV ranges are defined and converted, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.



