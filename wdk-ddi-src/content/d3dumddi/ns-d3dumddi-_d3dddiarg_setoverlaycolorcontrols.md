---
UID: NS:d3dumddi._D3DDDIARG_SETOVERLAYCOLORCONTROLS
title: "_D3DDDIARG_SETOVERLAYCOLORCONTROLS"
author: windows-driver-content
description: The D3DDDIARG_SETOVERLAYCOLORCONTROLS structure describes the parameters for changing an overlay's color-control settings.
old-location: display\d3dddiarg_setoverlaycolorcontrols.htm
old-project: display
ms.assetid: c8f04d2e-4c8c-4d1e-92e8-0f8722dbee5a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_D3DDDIARG_SETOVERLAYCOLORCONTROLS, d3dumddi/D3DDDIARG_SETOVERLAYCOLORCONTROLS, UMDisplayDriver_param_Structs_f6504b3e-8129-4936-add8-5bbf6ba8ee54.xml, D3DDDIARG_SETOVERLAYCOLORCONTROLS, D3DDDIARG_SETOVERLAYCOLORCONTROLS structure [Display Devices], display.d3dddiarg_setoverlaycolorcontrols"
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_SETOVERLAYCOLORCONTROLS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

