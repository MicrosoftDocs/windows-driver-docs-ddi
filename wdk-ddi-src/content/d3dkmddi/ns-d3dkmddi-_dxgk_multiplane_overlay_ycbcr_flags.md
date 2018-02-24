---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title: "_DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS"
author: windows-driver-content
description: Identifies YUV range and conversion info that describes a multiplane overlay.
old-location: display\dxgk_multiplane_overlay_ycbcr_flags.htm
old-project: display
ms.assetid: c3a463b1-fc6f-4834-87e5-1d694f2823f9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS, DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS structure [Display Devices], d3dkmddi/DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS, DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS, display.dxgk_multiplane_overlay_ycbcr_flags"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# _DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS structure


## -description


Identifies YUV range and conversion info that describes a multiplane overlay.


## -syntax


````
typedef struct _DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS {
  union {
    struct {
      UINT NominalRange  :1;
      UINT Bt709  :1;
      UINT xvYCC  :1;
      UINT Reserved  :29;
    };
    UINT   Value;
  };
} DXGK_MULTIPLANE_OVERLAY_YCbCr_FLAGS;
````


## -struct-fields




### -field NominalRange

If set, YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Bt709

If set, YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002).


### -field xvYCC

If set, YUV values contain xvYCC data, instead of conventional YCbCr data.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004).


### -field Reserved

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 29 bits (0xFFFFFFF8) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A 32-bit value that identifies the type of blend operation to perform.

