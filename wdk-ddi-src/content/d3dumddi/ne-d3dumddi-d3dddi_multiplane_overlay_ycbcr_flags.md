---
UID: NE:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
author: windows-driver-content
description: Identifies YUV range and conversion info that describes a multiplane overlay.
old-location: display\d3dddi_multiplane_overlay_ycbcr_flags.htm
tech.root: display
ms.assetid: d28170a4-2cf3-4e42-bc76-afdb8c3bce70
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration [Display Devices], D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, d3dumddi/D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, display.d3dddi_multiplane_overlay_ycbcr_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration


## -description


Identifies YUV range and conversion info that describes a multiplane overlay.


## -enum-fields




### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE

YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.


### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709

YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.


### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC

YUV values contain xvYCC data, instead of conventional YCbCr data.


## -remarks



For more info on how YUV ranges are defined and converted, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.



