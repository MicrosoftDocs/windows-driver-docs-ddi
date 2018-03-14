---
UID: NS:d3dkmddi._DXGK_GAMMARAMPCAPS
title: "_DXGK_GAMMARAMPCAPS"
author: windows-driver-content
description: The DXGK_GAMMARAMPCAPS structure identifies gamma-ramp capabilities of the display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_gammarampcaps.htm
old-project: display
ms.assetid: 3e160700-5d90-4241-8ed4-8d87b545b9c3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_GAMMARAMPCAPS, DXGK_GAMMARAMPCAPS structure [Display Devices], DmStructs_2f60099d-a359-41f4-b3d0-a7c0d0a6cca4.xml, _DXGK_GAMMARAMPCAPS, d3dkmddi/DXGK_GAMMARAMPCAPS, display.dxgk_gammarampcaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_GAMMARAMPCAPS
product: Windows
targetos: Windows
req.typenames: DXGK_GAMMARAMPCAPS
---

# _DXGK_GAMMARAMPCAPS structure


## -description


The DXGK_GAMMARAMPCAPS structure identifies gamma-ramp capabilities of the display miniport driver that the driver provides through a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


## -syntax


````
typedef struct _DXGK_GAMMARAMPCAPS {
  union {
    struct {
      UINT Gamma_Rgb256x3x16  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_GAMMARAMPCAPS;
````


## -struct-fields




### -field Gamma_Rgb256x3x16

A UINT value that specifies whether gamma ramp data is stored as 256 16-bit RGB values. Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).


### -field Reserved

This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.


#### - Value

A member in the union that DXGK_GAMMARAMPCAPS contains that can hold a 32-bit value that identifies gamma-ramp capabilities.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 


