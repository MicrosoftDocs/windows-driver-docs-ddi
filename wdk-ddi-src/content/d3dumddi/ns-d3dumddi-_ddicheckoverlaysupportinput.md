---
UID: NS:d3dumddi._DDICHECKOVERLAYSUPPORTINPUT
title: _DDICHECKOVERLAYSUPPORTINPUT (d3dumddi.h)
description: The DDICHECKOVERLAYSUPPORTINPUT structure describes an overlay display mode that the user-mode display driver uses to verify overlay support.
old-location: display\ddicheckoverlaysupportinput.htm
tech.root: display
ms.assetid: 5f15743a-1ea7-4260-b2cb-f2871acb27f9
ms.date: 05/10/2018
ms.keywords: D3D_other_Structs_194edebf-9bbd-465b-a731-ad3e10f6e809.xml, DDICHECKOVERLAYSUPPORTINPUT, DDICHECKOVERLAYSUPPORTINPUT structure [Display Devices], _DDICHECKOVERLAYSUPPORTINPUT, d3dumddi/DDICHECKOVERLAYSUPPORTINPUT, display.ddicheckoverlaysupportinput
f1_keywords:
 - "d3dumddi/DDICHECKOVERLAYSUPPORTINPUT"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DDICHECKOVERLAYSUPPORTINPUT is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DDICHECKOVERLAYSUPPORTINPUT
product:
- Windows
targetos: Windows
req.typenames: DDICHECKOVERLAYSUPPORTINPUT
---

# _DDICHECKOVERLAYSUPPORTINPUT structure


## -description


The DDICHECKOVERLAYSUPPORTINPUT structure describes an overlay display mode that the user-mode display driver uses to verify overlay support. 


## -struct-fields




### -field OverlayWidth

[in] The width of the overlay in pixels. 


### -field OverlayHeight

[in] The height of the overlay in pixels. 


### -field OverlayFormat


      [in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the overlay. 
     


### -field DisplayWidth

[in] The screen width of the display in pixels. 


### -field DisplayHeight

[in] The screen height of the display in pixels. 


### -field DisplayRefreshRate

[in] The refresh rate of the display. 


### -field DisplayFormat

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the display. 


### -field DisplayScanLineOrdering

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_scanlineordering">D3DDDI_SCANLINEORDERING</a>-typed value that indicates how the scan lines are drawn on the display. 


### -field DisplayRotation

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>-typed value that indicates how the display is oriented. 


## -remarks



The runtime specifies a pointer to a DDICHECKOVERLAYSUPPORTINPUT structure in the <b>pInfo</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure. The runtime also specifies the D3DDDICAPS_CHECKOVERLAYSUPPORT value in the <b>Type</b> member of D3DDDIARG_GETCAPS. The runtime specifies these values in a call to the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> function to determine if the driver supports the overlay that DDICHECKOVERLAYSUPPORTINPUT describes. The driver's <i>GetCaps</i> returns a pointer to a D3DOVERLAYCAPS structure that contains information about the capabilities of the overlay through the <b>pData</b> member of D3DDDIARG_GETCAPS if the driver supports the overlay.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_scanlineordering">D3DDDI_SCANLINEORDERING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>
 

 

