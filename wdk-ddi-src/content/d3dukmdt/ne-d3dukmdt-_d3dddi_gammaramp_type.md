---
UID: NE:d3dukmdt._D3DDDI_GAMMARAMP_TYPE
title: "_D3DDDI_GAMMARAMP_TYPE"
author: windows-driver-content
description: The D3DDDI_GAMMARAMP_TYPE enumeration indicates the type of gamma ramp used in a video present path.
old-location: display\d3dddi_gammaramp_type.htm
old-project: display
ms.assetid: 4261989f-5f29-4957-9633-ce2de14698fa
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DDDI_GAMMARAMP_DEFAULT, D3DDDI_GAMMARAMP_DXGI_1, D3DDDI_GAMMARAMP_MATRIX_3x4, D3DDDI_GAMMARAMP_RGB256x3x16, D3DDDI_GAMMARAMP_TYPE, D3DDDI_GAMMARAMP_TYPE enumeration [Display Devices], D3DDDI_GAMMARAMP_UNINITIALIZED, DmEnums_fc19c762-0156-4602-97ea-0b3865012161.xml, _D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_DEFAULT, d3dukmdt/D3DDDI_GAMMARAMP_DXGI_1, d3dukmdt/D3DDDI_GAMMARAMP_MATRIX_3x4, d3dukmdt/D3DDDI_GAMMARAMP_RGB256x3x16, d3dukmdt/D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_UNINITIALIZED, display.d3dddi_gammaramp_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_GAMMARAMP_TYPE
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_GAMMARAMP_TYPE
---

# _D3DDDI_GAMMARAMP_TYPE enumeration


## -description


The D3DDDI_GAMMARAMP_TYPE enumeration indicates the type of gamma ramp used in a video present path.


## -enum-fields




### -field D3DDDI_GAMMARAMP_UNINITIALIZED

Indicates that a variable of type D3DDDI_GAMMARAMP_TYPE has not yet been assigned a meaningful value.


### -field D3DDDI_GAMMARAMP_DEFAULT

Indicates the default gamma ramp.


### -field D3DDDI_GAMMARAMP_RGB256x3x16

Indicates that the gamma lookup table contains three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.


### -field D3DDDI_GAMMARAMP_DXGI_1

Indicates that the gamma lookup table is described by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544568">D3DDDI_GAMMA_RAMP_DXGI_1</a> structure. 


### -field D3DDDI_GAMMARAMP_MATRIX_3x4

Indicates that the colorspace transform is defined by a D3DDDI_3X4_COLORSPACE_TRANSFORM structure.


## -remarks



The <b>GammaRamp</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546014">D3DKMDT_GAMMA_RAMP</a> structure. The <b>Type</b> member of the D3DKMDT_GAMMA_RAMP structure is a D3DDDI_GAMMARAMP_TYPE value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545984">D3DKMDT_COLOR_BASIS</a>
 

 

