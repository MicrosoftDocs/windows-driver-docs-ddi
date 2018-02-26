---
UID: NS:d3dumddi._DXVADDI_PROCAMPVALUES
title: "_DXVADDI_PROCAMPVALUES"
author: windows-driver-content
description: The DXVADDI_PROCAMPVALUES structure describes the ProcAmp control adjustment values.
old-location: display\dxvaddi_procampvalues.htm
old-project: display
ms.assetid: bce6931d-af45-42aa-9be2-ded07f98c300
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, C, D, DXVA2_Structs_b731e88e-8f64-4199-9f75-9b5cba380aa8.xml, DXVADDI_PROCAMPVALUES, DXVADDI_PROCAMPVALUES structure [Display Devices], E, I, L, M, O, P, R, S, U, V, X, _, _DXVADDI_PROCAMPVALUES, d3dumddi/DXVADDI_PROCAMPVALUES, display.dxvaddi_procampvalues"
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
-	DXVADDI_PROCAMPVALUES
product: Windows
targetos: Windows
req.typenames: DXVADDI_PROCAMPVALUES
---

# _DXVADDI_PROCAMPVALUES structure


## -description


The DXVADDI_PROCAMPVALUES structure describes the ProcAmp control adjustment values.


## -syntax


````
typedef struct _DXVADDI_PROCAMPVALUES {
  DXVADDI_FIXED32 Brightness;
  DXVADDI_FIXED32 Contrast;
  DXVADDI_FIXED32 Hue;
  DXVADDI_FIXED32 Saturation;
} DXVADDI_PROCAMPVALUES;
````


## -struct-fields




### -field Brightness

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the brightness of the output image, as it is written to the destination surface.


### -field Contrast

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the contrast of the output image, as it is written to the destination surface.


### -field Hue

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the hue of the output image, as it is written to the destination surface.


### -field Saturation

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the saturation of the output image, as it is written to the destination surface.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_PROCAMPVALUES structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

