---
UID: NS:dxva._DXVA_Frequency
title: "_DXVA_Frequency"
author: windows-driver-content
description: The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.
old-location: display\dxva_frequency.htm
old-project: display
ms.assetid: 4e7d9746-7dae-4f53-9bf8-e0acc807306a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA_Frequency, DXVA_Frequency structure [Display Devices], _DXVA_Frequency, display.dxva_frequency, dxva/DXVA_Frequency, dxvaref_a36a3edd-8f65-4d6d-85d0-360e0f03e978.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	dxva.h
api_name:
-	DXVA_Frequency
product: Windows
targetos: Windows
req.typenames: DXVA_Frequency
---

# _DXVA_Frequency structure


## -description


The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.


## -syntax


````
typedef struct _DXVA_Frequency {
  DWORD Numerator;
  DWORD Denominator;
} DXVA_Frequency;
````


## -struct-fields




### -field Numerator

Specifies the numerator of the frequency fraction.


### -field Denominator

Specifies the denominator of the frequency fraction.

