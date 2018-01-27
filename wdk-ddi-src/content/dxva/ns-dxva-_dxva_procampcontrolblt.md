---
UID: NS:dxva._DXVA_ProcAmpControlBlt
title: _DXVA_ProcAmpControlBlt
author: windows-driver-content
description: The DXVA_ProcAmpControlBlt structure contains the ProcAmp adjustment data that is output to the destination surface.
old-location: display\dxva_procampcontrolblt.htm
old-project: display
ms.assetid: 93f321e1-a38b-43a2-bfbd-35411a62194e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxva/DXVA_ProcAmpControlBlt, DXVA_ProcAmpControlBlt, dxvaref_aaac59e6-334e-49a3-a599-facef11960e3.xml, display.dxva_procampcontrolblt, _DXVA_ProcAmpControlBlt, DXVA_ProcAmpControlBlt structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
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
-	dxva.h
apiname: 
-	DXVA_ProcAmpControlBlt
product: Windows
targetos: Windows
req.typenames: DXVA_ProcAmpControlBlt
---

# _DXVA_ProcAmpControlBlt structure


## -description


The DXVA_ProcAmpControlBlt structure contains the ProcAmp adjustment data that is output to the destination surface.


## -syntax


````
typedef struct _DXVA_ProcAmpControlBlt {
  DWORD Size;
  RECT  DstRect;
  RECT  SrcRect;
  FLOAT Alpha;
  FLOAT Brightness;
  FLOAT Contrast;
  FLOAT Hue;
  FLOAT Saturation;
} DXVA_ProcAmpControlBlt;
````


## -struct-fields




### -field Size

Specifies the size of this structure in bytes.


### -field DstRect

Specifies the destination rectangle as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure. The destination rectangle is required for subrectangle stretching. Support for stretching is optional and is reported by the <a href="..\dxva\ns-dxva-_dxva_procampcontrolcaps.md">DXVA_ProcAmpControlCaps</a> structure. Support for subrectangles is optional.


### -field SrcRect

Specifies the source rectangle as a RECT structure. The source rectangle is required for subrectangle stretching.sub Support for stretching is optional and is reported by the DXVA_ProcAmpControlCaps structure. Support for subrectangles is also optional.


### -field Alpha

Specifies the transparency of the output image as it is written to the destination surface. A value of 0.0F indicates transparent. A value of 1.0F indicates opaque.


### -field Brightness

Specifies the brightness of the output image as it is written to the destination surface.


### -field Contrast

Specifies the contrast of the output image as it is written to the destination surface.


### -field Hue

Specifies the hue of the output image as it is written to the destination surface.


### -field Saturation

Specifies the saturation of the output image as it is written to the destination surface.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_procampcontrolcaps.md">DXVA_ProcAmpControlCaps</a>

<a href="..\dxva\ns-dxva-_dxva_procampcontrolqueryrange.md">DXVA_ProcAmpControlQueryRange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ProcAmpControlBlt structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

