---
UID: NE:d3dumddi.D3DDDI_MARKERTYPE
title: D3DDDI_MARKERTYPE (d3dumddi.h)
description: Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.
old-location: display\d3dddi_markertype.htm
tech.root: display
ms.assetid: 55A48F87-B96C-42E7-B9B4-3C829097CAE9
ms.date: 05/10/2018
keywords: ["D3DDDI_MARKERTYPE enumeration"]
ms.keywords: D3DDDIMT_NONE, D3DDDIMT_PROFILE, D3DDDI_MARKERTYPE, D3DDDI_MARKERTYPE enumeration [Display Devices], d3dumddi/D3DDDIMT_NONE, d3dumddi/D3DDDIMT_PROFILE, d3dumddi/D3DDDI_MARKERTYPE, display.d3dddi_markertype
f1_keywords:
 - "d3dumddi/D3DDDI_MARKERTYPE"
 - "D3DDDI_MARKERTYPE"
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDI_MARKERTYPE
targetos: Windows
req.typenames: D3DDDI_MARKERTYPE
---

# D3DDDI_MARKERTYPE enumeration


## -description


Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.


## -enum-fields




### -field D3DDDIMT_NONE

No marker type is supported. This type is set on creation of the display device.


### -field D3DDDIMT_PROFILE

Profile mode, where the driver estimates the length of time the GPU takes to execute certain operations. The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.

See Remarks of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setmarkermode">pfnSetMarkerMode</a> function for more info.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setmarkermode">pfnSetMarkerMode</a>
 

 

