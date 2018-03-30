---
UID: NF:icm.WcsTranslateColors
title: WcsTranslateColors function
author: windows-driver-content
description: The WcsTranslateColors function translates an array of colors from the source color space to the destination color space as defined by a color transform.
old-location: print\wcstranslatecolors.htm
old-project: print
ms.assetid: 99843150-9e27-4f09-a3ba-5ff87d3f1c88
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WcsTranslateColors, WcsTranslateColors function [Print Devices], colorfnc_3fac2d89-165e-4d5e-8dd2-cd68f7a9a47a.xml, icm/WcsTranslateColors, print.wcstranslatecolors
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Included in Windows Vista and later.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Mscms.dll
api_name:
-	WcsTranslateColors
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsTranslateColors function


## -description


The <code>WcsTranslateColors</code> function translates an array of colors from the source color space to the destination color space as defined by a color transform.


## -parameters




### -param hColorTransform [in]

A handle to the WCS color transform to use.


### -param nColors [in]

The number of elements in the array pointed to by <i>pInputData</i> and <i>pOutputData</i>.


### -param nInputChannels [in]

The number of channels per element in the array pointed to by <i>pInputData</i>.


### -param cdtInput [in]

The input <a href="https://msdn.microsoft.com/library/windows/hardware/ff546006">COLORDATATYPE</a> color data type.


### -param cbInput [in]

The buffer size, in bytes, of <i>pInputData</i>.


### -param pInputData [in]

A pointer to an array of input colors.


### -param nOutputChannels [in]

The number of channels per element in the array pointed to by <i>pOutputData</i>.


### -param cdtOutput [in]

The output <a href="https://msdn.microsoft.com/library/windows/hardware/ff546006">COLORDATATYPE</a> color data type.


### -param cbOutput [in]

The buffer size, in bytes, of <i>pOutputData</i>.


### -param pOutputData [out]

A pointer to an array of colors that receives the results of the color translation.


## -remarks



If the input and the output color data types are not compatible with the color transform, this function will fail.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546006">COLORDATATYPE</a>
 

 

