---
UID: NS:d3dhal._DD_MULTISAMPLEQUALITYLEVELSDATA
title: _DD_MULTISAMPLEQUALITYLEVELSDATA (d3dhal.h)
description: DirectX 9.0 and later versions only. DD_MULTISAMPLEQUALITYLEVELSDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS.
old-location: display\dd_multisamplequalitylevelsdata.htm
tech.root: display
ms.assetid: ff8bc5d8-5d65-4752-9318-f775394ae2b9
ms.date: 05/10/2018
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA structure [Display Devices], _DD_MULTISAMPLEQUALITYLEVELSDATA, d3dhal/DD_MULTISAMPLEQUALITYLEVELSDATA, d3dstrct_6a515881-91b7-4072-bf6c-4e10153c1124.xml, display.dd_multisamplequalitylevelsdata
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- DD_MULTISAMPLEQUALITYLEVELSDATA
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# _DD_MULTISAMPLEQUALITYLEVELSDATA structure


## -description



   DirectX 9.0 and later versions only.
   

DD_MULTISAMPLEQUALITYLEVELSDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS.


## -struct-fields




### -field gdi2

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.


### -field Format

Uses a value from the D3DFORMAT enumeration to specify the surface format of the multiple-sampled render target.


### -field bFlip

Indicates the type of resolution. Set to <b>TRUE</b> (1) for flip-style resolution and to <b>FALSE</b> (0) for blt-style resolution.


### -field MSType

Uses a value from the D3DMULTISAMPLE_TYPE enumeration to specify the level of full-scene multisampling. If the display device supports maskable multisampling (more than one sample for a multiple-sample render-target format plus antialias support), the driver for the device must provide the number of quality levels for the D3DMULTISAMPLE_NONMASKABLE (1) enumerated value. 


### -field QualityLevels

Receives the number of multiple-sample quality levels that the driver supports for the given render-target format.


## -remarks



The driver assigns an integer from 1 to 8 to the <b>QualityLevels</b> member. If the driver fails, ignores this D3DGDI2_TYPE_GETMULTISAMPLEQUALITYLEVELS query, or returns a value that is out of range, but otherwise reports that it supports multisampling, then the runtime determines that the number of quality levels is 1. 

When the runtime calls a driver's <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549213(v=vs.85)">DdCanCreateSurface</a>, <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549263(v=vs.85)">DdCreateSurface</a>, or <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_createsurfaceex">D3dCreateSurfaceEx</a> functions to create a surface, the runtime encodes the number of multiple-sample quality levels into three bits (the DDSCAPS3_MULTISAMPLE_QUALITY_MASK mask) of the <b>dwCaps3</b> member of a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550292(v=vs.85)">DDSCAPS2</a> structure.

For more information about D3DFORMAT and D3DMULTISAMPLE_TYPE, see the DirectX SDK documentation.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_createsurfaceex">D3dCreateSurfaceEx</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff550292(v=vs.85)">DDSCAPS2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dhal/ns-d3dhal-_dd_getdriverinfo2data">DD_GETDRIVERINFO2DATA</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/ns-ddrawint-_dd_getdriverinfodata">DD_GETDRIVERINFODATA</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549213(v=vs.85)">DdCanCreateSurface</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff549263(v=vs.85)">DdCreateSurface</a>
 

 

