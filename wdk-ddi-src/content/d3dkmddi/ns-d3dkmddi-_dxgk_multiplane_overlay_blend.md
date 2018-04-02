---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_BLEND
title: "_DXGK_MULTIPLANE_OVERLAY_BLEND"
author: windows-driver-content
description: Identifies a blend operation to be performed on an overlay plane.
old-location: display\dxgk_multiplane_overlay_blend.htm
old-project: display
ms.assetid: e489919c-c0a7-4792-9758-ce7b587b13cc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_BLEND, DXGK_MULTIPLANE_OVERLAY_BLEND structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_BLEND, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_BLEND, display.dxgk_multiplane_overlay_blend
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_BLEND
product: Windows
targetos: Windows
req.typenames: DXGK_MULTIPLANE_OVERLAY_BLEND
---

# _DXGK_MULTIPLANE_OVERLAY_BLEND structure


## -description


Identifies a blend operation to be performed on an overlay plane.


## -struct-fields




### -field AlphaBlend

If set, the overlay plane should use the pre-multiplied alpha channel in this plane to blend it with the plane beneath.

If zero, the overlay plane should ignore data in the alpha channel and make the blended plane entirely opaque.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.

This member is reserved and should be set to zero.

Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - ColorKey

A value for the color key. 


#### - Value

A 32-bit value that identifies the type of blend operation to perform.

