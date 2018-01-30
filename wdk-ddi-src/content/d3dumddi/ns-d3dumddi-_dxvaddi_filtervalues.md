---
UID: NS:d3dumddi._DXVADDI_FILTERVALUES
title: "_DXVADDI_FILTERVALUES"
author: windows-driver-content
description: The DXVADDI_FILTERVALUES structure describes values that are related to a filter.
old-location: display\dxvaddi_filtervalues.htm
old-project: display
ms.assetid: 45273541-0638-4e8e-b6b7-5183b481ccc4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVADDI_FILTERVALUES structure [Display Devices], _DXVADDI_FILTERVALUES, display.dxvaddi_filtervalues, d3dumddi/DXVADDI_FILTERVALUES, DXVA2_Structs_1425eb3e-586d-4777-be61-8a73148286d4.xml, DXVADDI_FILTERVALUES
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
-	DXVADDI_FILTERVALUES
product: Windows
targetos: Windows
req.typenames: DXVADDI_FILTERVALUES
---

# _DXVADDI_FILTERVALUES structure


## -description


The DXVADDI_FILTERVALUES structure describes values that are related to a filter.


## -syntax


````
typedef struct _DXVADDI_FILTERVALUES {
  DXVADDI_FIXED32 Level;
  DXVADDI_FIXED32 Threshold;
  DXVADDI_FIXED32 Radius;
} DXVADDI_FILTERVALUES;
````


## -struct-fields




### -field Level

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the level of the filter.


### -field Threshold

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the threshold of the filter.


### -field Radius

[in] A <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_fixed32.md">DXVADDI_FIXED32</a> structure that specifies the radius of the filter.


## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_videoprocessblt.md">D3DDDIARG_VIDEOPROCESSBLT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_FILTERVALUES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

