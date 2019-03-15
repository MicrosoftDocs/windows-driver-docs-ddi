---
UID: NS:d3dkmdt._D3DKMDT_GAMMA_RAMP
title: _D3DKMDT_GAMMA_RAMP (d3dkmdt.h)
description: The D3DKMDT_GAMMA_RAMP structure contains descriptive information about a gamma lookup table and a pointer to the lookup table.
old-location: display\d3dkmdt_gamma_ramp.htm
tech.root: display
ms.assetid: 3a875a1e-ef4f-4851-9329-f1fd2aca261f
ms.date: 05/10/2018
ms.keywords: D3DKMDT_GAMMA_RAMP, D3DKMDT_GAMMA_RAMP structure [Display Devices], DmStructs_bb8721fc-b604-45e4-b3c8-ff27bda95e5b.xml, _D3DKMDT_GAMMA_RAMP, d3dkmdt/D3DKMDT_GAMMA_RAMP, display.d3dkmdt_gamma_ramp
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
- d3dkmdt.h
api_name:
- D3DKMDT_GAMMA_RAMP
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_GAMMA_RAMP
---

# _D3DKMDT_GAMMA_RAMP structure


## -description


The D3DKMDT_GAMMA_RAMP structure contains descriptive information about a gamma lookup table and a pointer to the lookup table.


## -struct-fields




### -field Type

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544565">D3DDDI_GAMMARAMP_TYPE</a> enumerator that specifies the format of the lookup table. 


### -field DataSize

The size, in bytes, of the lookup table pointed to by <i>Data</i>.


### -field Data

[in] A union that contains one of the following ways to access the lookup table data depending on the value in the Type member:


### -field Data.pRgb256x3x16

If <b>Type</b> is equal to D3DDDI_GAMMARAMP_RGB256x3x16, this member is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544571">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> structure that contains the lookup table. 


### -field Data.pDxgi1

If <b>Type</b> is equal to D3DDDI_GAMMARAMP_DXGI_1, this member is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544568">D3DDDI_GAMMA_RAMP_DXGI_1</a> structure that contains the lookup table. 


### -field Data.p3x4

Pointer to a D3DDDI_3x4_COLORSPACE_TRANSFORM which describes the 3 by 4 matrix color space transform to be applied.


### -field Data.pRaw

This member provides an alternative way to access the lookup table data. For example, for copying the lookup table, VOID* might be more convenient than D3DDDI_GAMMA_RAMP_RGB256x3x16.


## -remarks



The <b>GammaRamp</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_GAMMA_RAMP structure.



