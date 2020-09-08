---
UID: NS:dxva._DXVA_Frequency
title: _DXVA_Frequency (dxva.h)
description: The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.
old-location: display\dxva_frequency.htm
tech.root: display
ms.assetid: 4e7d9746-7dae-4f53-9bf8-e0acc807306a
ms.date: 05/10/2018
keywords: ["DXVA_Frequency structure"]
ms.keywords: DXVA_Frequency, DXVA_Frequency structure [Display Devices], _DXVA_Frequency, display.dxva_frequency, dxva/DXVA_Frequency, dxvaref_a36a3edd-8f65-4d6d-85d0-360e0f03e978.xml
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
targetos: Windows
req.typenames: DXVA_Frequency
f1_keywords:
 - _DXVA_Frequency
 - dxva/_DXVA_Frequency
 - DXVA_Frequency
 - dxva/DXVA_Frequency
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - dxva.h
api_name:
 - DXVA_Frequency
---

# _DXVA_Frequency structure


## -description

The DXVA_Frequency structure is sent by the host decoder to the driver to specify the video frame rate, in Hz. For example, NTSC TV is 60000 over 1001.

## -struct-fields

### -field Numerator

Specifies the numerator of the frequency fraction.

### -field Denominator

Specifies the denominator of the frequency fraction.

