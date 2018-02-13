---
UID: NF:icm.WcsTranslateColors
title: WcsTranslateColors function
author: windows-driver-content
description: The WcsTranslateColors function translates an array of colors from the source color space to the destination color space as defined by a color transform.
old-location: print\wcstranslatecolors.htm
old-project: print
ms.assetid: 99843150-9e27-4f09-a3ba-5ff87d3f1c88
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.wcstranslatecolors, WcsTranslateColors, icm/WcsTranslateColors, colorfnc_3fac2d89-165e-4d5e-8dd2-cd68f7a9a47a.xml, WcsTranslateColors function [Print Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Mscms.dll
apiname:
-	WcsTranslateColors
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsTranslateColors function


## -description


The <code>WcsTranslateColors</code> function translates an array of colors from the source color space to the destination color space as defined by a color transform.


## -syntax


````
BOOL WcsTranslateColors(
  _In_  HTRANSFORM    hColorTransform,
  _In_  DWORD         nColors,
  _In_  DWORD         nInputChannels,
  _In_  COLORDATATYPE cdtInput,
  _In_  DWORD         cbInput,
  _In_  PVOID         pInputData,
  _In_  DWORD         nOutputChannels,
  _In_  COLORDATATYPE cdtOutput,
  _In_  DWORD         cbOutput,
  _Out_ PVOID         pOutputData
);
````


## -parameters




### -param hColorTransform [in]

A handle to the WCS color transform to use.


### -param nColors [in]

The number of elements in the array pointed to by <i>pInputData</i> and <i>pOutputData</i>.


### -param nInputChannels [in]

The number of channels per element in the array pointed to by <i>pInputData</i>.


### -param cdtInput [in]

The input <a href="..\icm\ne-icm-colordatatype.md">COLORDATATYPE</a> color data type.


### -param cbInput [in]

The buffer size, in bytes, of <i>pInputData</i>.


### -param pInputData [in]

A pointer to an array of input colors.


### -param nOutputChannels [in]

The number of channels per element in the array pointed to by <i>pOutputData</i>.


### -param cdtOutput [in]

The output <a href="..\icm\ne-icm-colordatatype.md">COLORDATATYPE</a> color data type.


### -param cbOutput [in]

The buffer size, in bytes, of <i>pOutputData</i>.


### -param pOutputData [out]

A pointer to an array of colors that receives the results of the color translation.


## -remarks



If the input and the output color data types are not compatible with the color transform, this function will fail.




## -see-also

<a href="..\icm\ne-icm-colordatatype.md">COLORDATATYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WcsTranslateColors function%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

