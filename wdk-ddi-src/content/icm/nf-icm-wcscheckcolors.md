---
UID: NF:icm.WcsCheckColors
title: WcsCheckColors function (icm.h)
description: The WcsCheckColors function determines whether the colors in an array lie within the output gamut of a specified WCS color transform.
old-location: print\wcscheckcolors.htm
tech.root: print
ms.assetid: 1254b0d4-cb72-4171-b09d-f0bca58a137a
ms.date: 08/13/2020
keywords: ["WcsCheckColors function"]
ms.keywords: WcsCheckColors, WcsCheckColors function [Print Devices], colorfnc_abd03c7d-c516-4c81-a0ff-df351cac753e.xml, icm/WcsCheckColors, print.wcscheckcolors
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
- WcsCheckColors
targetos: Windows
req.typenames: 
---

# WcsCheckColors function

## -description

The **WcsCheckColors** function determines whether the colors in an array lie within the output gamut of a specified WCS color transform.

## -parameters

### -param hColorTransform [in]

A handle to the WCS color transform to use.

### -param nColors [in]

The number of elements in the array pointed to by *pInputData* and *paResult*.

### -param nInputChannels [in]

The number of channels per element in the array pointed to by *pInputData*.

### -param cdtInput [in]

The input COLORDATATYPE color data type.

### -param cbInput [in]

The buffer size of *pInputData*.

### -param pInputData [in]

A pointer to an array of input colors. Colors in this array correspond to the color space of the source profile.

### -param paResult [out]

A pointer to an array of *nColors* bytes that receives the results of the test.

## -remarks

If the input and the output color data types are not compatible with the color transform, this function will convert the input color data as required.

This function will fail if an ICC transform is used.
