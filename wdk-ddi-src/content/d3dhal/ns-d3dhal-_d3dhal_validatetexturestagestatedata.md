---
UID: NS:d3dhal._D3DHAL_VALIDATETEXTURESTAGESTATEDATA
title: _D3DHAL_VALIDATETEXTURESTAGESTATEDATA (d3dhal.h)
description: The D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure contains the information required for the driver to determine and return its ability to support multitexturing using the current state.
old-location: display\d3dhal_validatetexturestagestatedata.htm
tech.root: display
ms.assetid: 25534f3b-5da8-47e0-a956-6d1849c40a3d
ms.date: 05/10/2018
keywords: ["D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure"]
ms.keywords: "*LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, D3DHAL_VALIDATETEXTURESTAGESTATEDATA, D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure [Display Devices], LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA structure pointer [Display Devices], _D3DHAL_VALIDATETEXTURESTAGESTATEDATA, d3dhal/D3DHAL_VALIDATETEXTURESTAGESTATEDATA, d3dhal/LPD3DHAL_VALIDATETEXTURESTAGESTATEDATA, d3dstrct_1f23a380-4c92-44c1-a2ae-7e0558fad221.xml, display.d3dhal_validatetexturestagestatedata"
f1_keywords:
 - "d3dhal/D3DHAL_VALIDATETEXTURESTAGESTATEDATA"
 - "D3DHAL_VALIDATETEXTURESTAGESTATEDATA"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DHAL_VALIDATETEXTURESTAGESTATEDATA
targetos: Windows
req.typenames: D3DHAL_VALIDATETEXTURESTAGESTATEDATA
---

# _D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure


## -description


The D3DHAL_VALIDATETEXTURESTAGESTATEDATA structure contains the information required for the driver to determine and return its ability to support multitexturing using the current state.


## -struct-fields




### -field dwhContext

Specifies the context ID of the Direct3D device.


### -field dwFlags

Currently set to zero and should be ignored by the driver.


### -field dwReserved

Reserved for system use and should be ignored by the driver.


### -field dwNumPasses

Specifies the location where the driver should write the number of passes required by the hardware to perform the blending operations.


### -field ddrval

Specifies the location where the driver writes the return value of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_validatetexturestagestatecb">D3dValidateTextureStageState</a> function. A return code of D3D_OK indicates success. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/return-codes-for-direct3d-driver-callbacks">Return Codes for Direct3D Driver Callbacks</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_validatetexturestagestatecb">D3dValidateTextureStageState</a>
 

 

