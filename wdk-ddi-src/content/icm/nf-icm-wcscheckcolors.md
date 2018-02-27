---
UID: NF:icm.WcsCheckColors
title: WcsCheckColors function
author: windows-driver-content
description: The WcsCheckColors function determines whether the colors in an array lie within the output gamut of a specified WCS color transform.
old-location: print\wcscheckcolors.htm
old-project: print
ms.assetid: 1254b0d4-cb72-4171-b09d-f0bca58a137a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: WcsCheckColors, WcsCheckColors function [Print Devices], colorfnc_abd03c7d-c516-4c81-a0ff-df351cac753e.xml, icm/WcsCheckColors, print.wcscheckcolors
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
-	WcsCheckColors
product: Windows
targetos: Windows
req.typenames: WCS_PROFILE_MANAGEMENT_SCOPE
---

# WcsCheckColors function


## -description


The <code>WcsCheckColors</code> function determines whether the colors in an array lie within the output gamut of a specified WCS color transform.


## -syntax


````
BOOL WcsCheckColors(
  _In_  HTRANSFORM    hColorTransform,
  _In_  DWORD         nColors,
  _In_  DWORD         nInputChannels,
  _In_  COLORDATATYPE cdtInput,
  _In_  DWORD         cbInput,
  _In_  PVOID         pInputData,
  _Out_ PBYTE         paResult
);
````


## -parameters




### -param hColorTransform [in]

A handle to the WCS color transform to use.


### -param nColors [in]

The number of elements in the array pointed to by <i>pInputData</i> and <i>paResult</i>.


### -param nInputChannels [in]

The number of channels per element in the array pointed to by <i>pInputData</i>.


### -param cdtInput [in]

The input COLORDATATYPE color data type.


### -param cbInput [in]

The buffer size of <i>pInputData</i>.


### -param pInputData [in]

A pointer to an array of input colors. Colors in this array correspond to the color space of the source profile.


### -param paResult [out]

A pointer to an array of <i>nColors</i> bytes that receives the results of the test.


## -remarks



If the input and the output color data types are not compatible with the color transform, this function will convert the input color data as required.

This function will fail if an ICC transform is used.



