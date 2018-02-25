---
UID: NS:dxva._DXVA_VideoPropertyRange
title: "_DXVA_VideoPropertyRange"
author: windows-driver-content
description: The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.
old-location: display\dxva_videopropertyrange.htm
old-project: display
ms.assetid: e78fa9ba-7573-47db-b4d8-9b7584d5b432
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *LPDXVA_VideoPropertyRange, ,, A, D, DXVA_VideoPropertyRange, DXVA_VideoPropertyRange structure [Display Devices], L, LPDXVA_VideoPropertyRange, LPDXVA_VideoPropertyRange structure pointer [Display Devices], P, R, V, X, _, _DXVA_VideoPropertyRange, a, d, display.dxva_videopropertyrange, dxva/DXVA_VideoPropertyRange, dxva/LPDXVA_VideoPropertyRange, dxvaref_0e7bc2aa-0404-4025-908a-5d4c528e020b.xml, e, g, i, n, o, p, r, t, y"
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
-	DXVA_VideoPropertyRange
product: Windows
targetos: Windows
req.typenames: DXVA_VideoPropertyRange, *LPDXVA_VideoPropertyRange
---

# _DXVA_VideoPropertyRange structure


## -description


The DXVA_VideoPropertyRange structure specifies the range of allowed values for ProcAmp control properties.


## -syntax


````
typedef struct _DXVA_VideoPropertyRange {
  FLOAT MinValue;
  FLOAT MaxValue;
  FLOAT DefaultValue;
  FLOAT StepSize;
} DXVA_VideoPropertyRange, *LPDXVA_VideoPropertyRange;
````


## -struct-fields




### -field MinValue

Specifies the minimum value allowed for a given property.


### -field MaxValue

Specifies the maximum value allowed for a given property.


### -field DefaultValue

Specifies the default value for a given property.


### -field StepSize

Specifies the step size increment for a given property.


## -see-also

<a href="..\dxva\ns-dxva-_dxva_videodesc.md">DXVA_VideoDesc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoPropertyRange structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

