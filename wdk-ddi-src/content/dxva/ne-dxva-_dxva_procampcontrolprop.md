---
UID: NE:dxva._DXVA_ProcAmpControlProp
title: "_DXVA_ProcAmpControlProp"
author: windows-driver-content
description: The DXVA_ProcAmpControlProp enumeration is used to determine the required ProcAmp control adjustments.
old-location: display\dxva_procampcontrolprop.htm
old-project: display
ms.assetid: ce1bae9b-1cc3-45ea-bf46-8aa7ed0362f6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVA_ProcAmp_None, dxva/DXVA_ProcAmp_Hue, DXVA_ProcAmp_Contrast, dxva/DXVA_ProcAmp_Brightness, DXVA_ProcAmp_Brightness, DXVA_ProcAmp_Saturation, dxva/DXVA_ProcAmp_Saturation, DXVA_ProcAmp_Hue, dxvaref_0bce43bc-3bb3-4c7a-8d83-16db2a513905.xml, dxva/DXVA_ProcAmp_None, _DXVA_ProcAmpControlProp, display.dxva_procampcontrolprop, dxva/DXVA_ProcAmp_Contrast, dxva/DXVA_ProcAmpControlProp, DXVA_ProcAmpControlProp, DXVA_ProcAmpControlProp enumeration [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	DXVA_ProcAmpControlProp
product: Windows
targetos: Windows
req.typenames: DXVA_ProcAmpControlProp
---

# _DXVA_ProcAmpControlProp enumeration


## -description


The DXVA_ProcAmpControlProp enumeration is used to determine the required ProcAmp control adjustments.


## -syntax


````
typedef enum _DXVA_ProcAmpControlProp { 
  DXVA_ProcAmp_None        = 0x0000,
  DXVA_ProcAmp_Brightness  = 0x0001,
  DXVA_ProcAmp_Contrast    = 0x0002,
  DXVA_ProcAmp_Hue         = 0x0004,
  DXVA_ProcAmp_Saturation  = 0x0008
} DXVA_ProcAmpControlProp;
````


## -enum-fields




### -field DXVA_ProcAmp_None

Specifies that no ProcAmp properties are used. 


### -field DXVA_ProcAmp_Brightness

Specifies that the ProcAmp brightness property is used. 


### -field DXVA_ProcAmp_Contrast

Specifies that the ProcAmp contrast property is used. 


### -field DXVA_ProcAmp_Hue

Specifies that the ProcAmp hue property is used. 


### -field DXVA_ProcAmp_Saturation

Specifies that the ProcAmp saturation property is used.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_procampcontrolqueryrange.md">DXVA_ProcAmpControlQueryRange</a>



<a href="..\dxva\ns-dxva-_dxva_procampcontrolcaps.md">DXVA_ProcAmpControlCaps</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ProcAmpControlProp enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

