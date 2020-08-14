---
UID: NF:icm.WcsTranslateColors
title: WcsTranslateColors function (icm.h)
description: The WcsTranslateColors function translates an array of colors from the source color space to the destination color space as defined by a color transform.
old-location: print\wcstranslatecolors.htm
tech.root: print
ms.assetid: 99843150-9e27-4f09-a3ba-5ff87d3f1c88
ms.date: 08/14/2020
keywords: ["WcsTranslateColors function"]
ms.keywords: WcsTranslateColors, WcsTranslateColors function [Print Devices], colorfnc_3fac2d89-165e-4d5e-8dd2-cd68f7a9a47a.xml, icm/WcsTranslateColors, print.wcstranslatecolors
req.header: icm.h
req.include-header: 
req.target-type: Universal
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Mscms.dll
api_name:
- WcsTranslateColors
targetos: Windows
req.typenames: 
---

# WcsTranslateColors function

## -description

The **WcsTranslateColors** function translates an array of colors from the source color space to the destination color space as defined by a color transform.

## -parameters

### -param hColorTransform [in]

A handle to the WCS color transform to use.

### -param nColors [in]

The number of elements in the array pointed to by *pInputData* and *pOutputData*.

### -param nInputChannels [in]

The number of channels per element in the array pointed to by *pInputData*.

### -param cdtInput [in]

The input [COLORDATATYPE](https://docs.microsoft.com/previous-versions/ff546006(v=vs.85)) color data type.

### -param cbInput [in]

The buffer size, in bytes, of *pInputData*.

### -param pInputData [in]

A pointer to an array of input colors.

### -param nOutputChannels [in]

The number of channels per element in the array pointed to by *pOutputData*.

### -param cdtOutput [in]

The output [COLORDATATYPE](https://docs.microsoft.com/previous-versions/ff546006(v=vs.85)) color data type.

### -param cbOutput [in]

The buffer size, in bytes, of *pOutputData*.

### -param pOutputData [out]

A pointer to an array of colors that receives the results of the color translation.

## -remarks

If the input and the output color data types are not compatible with the color transform, this function will fail.

## -see-also

[COLORDATATYPE](https://docs.microsoft.com/previous-versions/ff546006(v=vs.85))
