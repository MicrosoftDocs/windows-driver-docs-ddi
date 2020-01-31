---
UID: NS:d3dumddi._D3DDDIARG_GETOVERLAYCOLORCONTROLS
title: _D3DDDIARG_GETOVERLAYCOLORCONTROLS (d3dumddi.h)
description: The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings.
old-location: display\d3dddiarg_getoverlaycolorcontrols.htm
tech.root: display
ms.assetid: 63d14667-7409-40c8-af03-e4ffedd73e7e
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_GETOVERLAYCOLORCONTROLS, D3DDDIARG_GETOVERLAYCOLORCONTROLS structure [Display Devices], UMDisplayDriver_param_Structs_eedf1607-a208-42ba-8d05-6151e489ee8f.xml, _D3DDDIARG_GETOVERLAYCOLORCONTROLS, d3dumddi/D3DDDIARG_GETOVERLAYCOLORCONTROLS, display.d3dddiarg_getoverlaycolorcontrols
f1_keywords:
 - "d3dumddi/D3DDDIARG_GETOVERLAYCOLORCONTROLS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDIARG_GETOVERLAYCOLORCONTROLS
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETOVERLAYCOLORCONTROLS
---

# _D3DDDIARG_GETOVERLAYCOLORCONTROLS structure


## -description


The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings. 


## -struct-fields




### -field hOverlay

[in] A handle to the overlay that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols">GetOverlayColorControls</a> retrieves color-control settings for.


### -field hResource

[in] A handle to the resource that is associated with the overlay that <b>hOverlay</b> specifies.


### -field ColorControls

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlaycolorcontrols">D3DDDI_OVERLAYCOLORCONTROLS</a> structure that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols">GetOverlayColorControls</a> populates with color-control settings.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_overlaycolorcontrols">D3DDDI_OVERLAYCOLORCONTROLS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols">GetOverlayColorControls</a>
 

 

