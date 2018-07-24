---
UID: NS:d3dumddi._DXVADDI_PVP_SETKEY
title: "_DXVADDI_PVP_SETKEY"
author: windows-driver-content
description: The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame.
old-location: display\dxvaddi_pvp_setkey.htm
tech.root: display
ms.assetid: 3707f9c9-109e-4ac2-bc34-c9f4f7651306
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_fbd26ed2-13ce-4f15-a7de-544f6f5fac33.xml, DXVADDI_PVP_SETKEY, DXVADDI_PVP_SETKEY structure [Display Devices], _DXVADDI_PVP_SETKEY, d3dumddi/DXVADDI_PVP_SETKEY, display.dxvaddi_pvp_setkey
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
-	DXVADDI_PVP_SETKEY
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_PVP_SETKEY
---

# _DXVADDI_PVP_SETKEY structure


## -description


The DXVADDI_PVP_SETKEY structure describes a key that the decode device uses to start decoding a frame. 


## -struct-fields




### -field ContentKey

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff562922">DXVADDI_PVP_KEY128</a> structure that contains the 128-bit key.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542987">D3DDDIARG_DECODEBEGINFRAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562922">DXVADDI_PVP_KEY128</a>



<a href="https://msdn.microsoft.com/3e6153aa-7b21-429d-8908-1ff3a4d25e17">DecodeBeginFrame</a>
 

 

