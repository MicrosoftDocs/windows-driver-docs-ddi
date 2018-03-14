---
UID: NS:d3dumddi._D3DDDIARG_SETOVERLAYCOLORCONTROLS
title: "_D3DDDIARG_SETOVERLAYCOLORCONTROLS"
author: windows-driver-content
description: The D3DDDIARG_SETOVERLAYCOLORCONTROLS structure describes the parameters for changing an overlay's color-control settings.
old-location: display\d3dddiarg_setoverlaycolorcontrols.htm
old-project: display
ms.assetid: c8f04d2e-4c8c-4d1e-92e8-0f8722dbee5a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_SETOVERLAYCOLORCONTROLS, D3DDDIARG_SETOVERLAYCOLORCONTROLS structure [Display Devices], UMDisplayDriver_param_Structs_f6504b3e-8129-4936-add8-5bbf6ba8ee54.xml, _D3DDDIARG_SETOVERLAYCOLORCONTROLS, d3dumddi/D3DDDIARG_SETOVERLAYCOLORCONTROLS, display.d3dddiarg_setoverlaycolorcontrols
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
-	D3DDDIARG_SETOVERLAYCOLORCONTROLS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_SETOVERLAYCOLORCONTROLS
---

# _D3DDDIARG_SETOVERLAYCOLORCONTROLS structure


## -description


The D3DDDIARG_SETOVERLAYCOLORCONTROLS structure describes the parameters for changing an overlay's color-control settings. 


## -syntax


````
typedef struct _D3DDDIARG_SETOVERLAYCOLORCONTROLS {
  HANDLE                      hOverlay;
  HANDLE                      hResource;
  D3DDDI_OVERLAYCOLORCONTROLS ColorControls;
} D3DDDIARG_SETOVERLAYCOLORCONTROLS;
````


## -struct-fields




### -field hOverlay

[in] A handle to the overlay that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setoverlaycolorcontrols.md">SetOverlayColorControls</a> changes color-control settings for.


### -field hResource

[in] A handle to the resource that is associated with the overlay that <b>hOverlay</b> specifies.


### -field ColorControls

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrols.md">D3DDDI_OVERLAYCOLORCONTROLS</a> structure that contains color-control settings.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrols.md">D3DDDI_OVERLAYCOLORCONTROLS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setoverlaycolorcontrols.md">SetOverlayColorControls</a>



 

 


