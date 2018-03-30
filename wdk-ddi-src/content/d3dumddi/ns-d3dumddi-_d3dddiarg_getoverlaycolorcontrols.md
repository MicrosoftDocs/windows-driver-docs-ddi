---
UID: NS:d3dumddi._D3DDDIARG_GETOVERLAYCOLORCONTROLS
title: "_D3DDDIARG_GETOVERLAYCOLORCONTROLS"
author: windows-driver-content
description: The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings.
old-location: display\d3dddiarg_getoverlaycolorcontrols.htm
old-project: display
ms.assetid: 63d14667-7409-40c8-af03-e4ffedd73e7e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_GETOVERLAYCOLORCONTROLS, D3DDDIARG_GETOVERLAYCOLORCONTROLS structure [Display Devices], UMDisplayDriver_param_Structs_eedf1607-a208-42ba-8d05-6151e489ee8f.xml, _D3DDDIARG_GETOVERLAYCOLORCONTROLS, d3dumddi/D3DDDIARG_GETOVERLAYCOLORCONTROLS, display.d3dddiarg_getoverlaycolorcontrols
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
-	D3DDDIARG_GETOVERLAYCOLORCONTROLS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETOVERLAYCOLORCONTROLS
---

# _D3DDDIARG_GETOVERLAYCOLORCONTROLS structure


## -description


The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings. 


## -struct-fields




### -field hOverlay

[in] A handle to the overlay that <a href="https://msdn.microsoft.com/23b15bb5-4394-406b-8869-f9d1e4e2b539">GetOverlayColorControls</a> retrieves color-control settings for.


### -field hResource

[in] A handle to the resource that is associated with the overlay that <b>hOverlay</b> specifies.


### -field ColorControls

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544612">D3DDDI_OVERLAYCOLORCONTROLS</a> structure that <a href="https://msdn.microsoft.com/23b15bb5-4394-406b-8869-f9d1e4e2b539">GetOverlayColorControls</a> populates with color-control settings.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544612">D3DDDI_OVERLAYCOLORCONTROLS</a>



<a href="https://msdn.microsoft.com/23b15bb5-4394-406b-8869-f9d1e4e2b539">GetOverlayColorControls</a>
 

 

