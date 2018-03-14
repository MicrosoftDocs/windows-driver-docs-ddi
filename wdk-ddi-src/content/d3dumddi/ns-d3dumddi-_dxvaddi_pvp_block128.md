---
UID: NS:d3dumddi._DXVADDI_PVP_BLOCK128
title: "_DXVADDI_PVP_BLOCK128"
author: windows-driver-content
description: The DXVADDI_PVP_KEY128 structure contains a 128-bit key that the decode device uses to start decoding a frame.
old-location: display\dxvaddi_pvp_key128.htm
old-project: display
ms.assetid: c4c65d1f-2531-4804-8a86-160b1ddfd692
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_1384e44e-aa25-470a-93bb-3e20b5885bdb.xml, DXVADDI_PVP_BLOCK128, DXVADDI_PVP_BLOCK128 structure [Display Devices], DXVADDI_PVP_KEY128, DXVADDI_PVP_KEY128 structure [Display Devices], _DXVADDI_PVP_BLOCK128, d3dumddi/DXVADDI_PVP_KEY128, display.dxvaddi_pvp_key128
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	DXVADDI_PVP_BLOCK128
product: Windows
targetos: Windows
req.typenames: DXVADDI_PVP_BLOCK128, DXVADDI_PVP_KEY128
---

# _DXVADDI_PVP_BLOCK128 structure


## -description


The DXVADDI_PVP_KEY128 structure contains a 128-bit key that the decode device uses to start decoding a frame. 


## -syntax


````
typedef struct _DXVADDI_PVP_BLOCK128 {
  BYTE Data[16];
} DXVADDI_PVP_BLOCK128, DXVADDI_PVP_KEY128;
````


## -struct-fields




### -field Data

[in] An array of 16 bytes that describes the 128-bit key that is used to start decoding.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodebeginframe.md">D3DDDIARG_DECODEBEGINFRAME</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_setkey.md">DXVADDI_PVP_SETKEY</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>



 

 


