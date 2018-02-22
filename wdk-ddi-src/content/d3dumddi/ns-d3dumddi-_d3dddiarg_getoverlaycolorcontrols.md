---
UID: NS:d3dumddi._D3DDDIARG_GETOVERLAYCOLORCONTROLS
title: "_D3DDDIARG_GETOVERLAYCOLORCONTROLS"
author: windows-driver-content
description: The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings.
old-location: display\d3dddiarg_getoverlaycolorcontrols.htm
old-project: display
ms.assetid: 63d14667-7409-40c8-af03-e4ffedd73e7e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DDDIARG_GETOVERLAYCOLORCONTROLS, display.d3dddiarg_getoverlaycolorcontrols, d3dumddi/D3DDDIARG_GETOVERLAYCOLORCONTROLS, D3DDDIARG_GETOVERLAYCOLORCONTROLS, UMDisplayDriver_param_Structs_eedf1607-a208-42ba-8d05-6151e489ee8f.xml, D3DDDIARG_GETOVERLAYCOLORCONTROLS structure [Display Devices]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	D3DDDIARG_GETOVERLAYCOLORCONTROLS
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETOVERLAYCOLORCONTROLS
---

# _D3DDDIARG_GETOVERLAYCOLORCONTROLS structure


## -description


The D3DDDIARG_GETOVERLAYCOLORCONTROLS structure describes the parameters for retrieving an overlay's color-control settings. 


## -syntax


````
typedef struct _D3DDDIARG_GETOVERLAYCOLORCONTROLS {
  HANDLE                      hOverlay;
  HANDLE                      hResource;
  D3DDDI_OVERLAYCOLORCONTROLS ColorControls;
} D3DDDIARG_GETOVERLAYCOLORCONTROLS;
````


## -struct-fields




### -field hOverlay

[in] A handle to the overlay that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols.md">GetOverlayColorControls</a> retrieves color-control settings for.


### -field hResource

[in] A handle to the resource that is associated with the overlay that <b>hOverlay</b> specifies.


### -field ColorControls

[out] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrols.md">D3DDDI_OVERLAYCOLORCONTROLS</a> structure that <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols.md">GetOverlayColorControls</a> populates with color-control settings.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlaycolorcontrols.md">D3DDDI_OVERLAYCOLORCONTROLS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getoverlaycolorcontrols.md">GetOverlayColorControls</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_GETOVERLAYCOLORCONTROLS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

