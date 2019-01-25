---
UID: NS:d3dhal._D3DHAL_DP2SETPRIORITY
title: "_D3DHAL_DP2SETPRIORITY" (d3dhal.h)
description: The D3DHAL_DP2SETPRIORITY structure is used to inform the driver of the priority of the texture specified by the handle dwDDDestSurface.
old-location: display\d3dhal_dp2setpriority.htm
tech.root: display
ms.assetid: 5101c150-b294-4bf4-b33c-f0fe0f54d727
ms.date: 05/10/2018
ms.keywords: "*LPD3DHAL_DP2SETPRIORITY, D3DHAL_DP2SETPRIORITY, D3DHAL_DP2SETPRIORITY structure [Display Devices], LPD3DHAL_DP2SETPRIORITY, LPD3DHAL_DP2SETPRIORITY structure pointer [Display Devices], _D3DHAL_DP2SETPRIORITY, d3dhal/D3DHAL_DP2SETPRIORITY, d3dhal/LPD3DHAL_DP2SETPRIORITY, d3dstrct_e6462000-a8f1-4181-ba23-4cda08b1edce.xml, display.d3dhal_dp2setpriority"
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2SETPRIORITY
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETPRIORITY
---

# _D3DHAL_DP2SETPRIORITY structure


## -description


The D3DHAL_DP2SETPRIORITY structure is used to inform the driver of the priority of the texture specified by the handle <b>dwDDDestSurface</b>.


## -struct-fields




### -field dwDDSurface

Specifies the handle of the texture. 


### -field dwPriority

Specifies the priority of the <b>dwDDDestSurface</b> texture. A texture's priority value can be set anywhere in the range from 0 to 0xFFFFFFFF.


## -remarks



Drivers are notified of handles at texture creation time. The driver can expect to receive priority notifications only for driver-managed textures.

Priorities determine when managed textures are to be evicted from memory. A texture assigned a low priority is evicted before a texture with a high priority. If two textures have the same priority, the texture that was used more recently is kept in memory; the other texture is evicted. 



