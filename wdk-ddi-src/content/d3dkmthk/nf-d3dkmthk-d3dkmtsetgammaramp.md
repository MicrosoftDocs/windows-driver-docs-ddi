---
UID: NF:d3dkmthk.D3DKMTSetGammaRamp
title: D3DKMTSetGammaRamp function
author: windows-driver-content
description: The D3DKMTSetGammaRamp function sets the gamma ramp.
old-location: display\d3dkmtsetgammaramp.htm
ms.assetid: 48f1d2ba-747a-4588-8238-db6ac2aa89d6
ms.date: 05/10/2018
ms.keywords: D3DKMTSetGammaRamp, D3DKMTSetGammaRamp function [Display Devices], OpenGL_Functions_4d684cea-8528-489d-bc35-b70a5f05a57b.xml, d3dkmthk/D3DKMTSetGammaRamp, display.d3dkmtsetgammaramp
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSetGammaRamp
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# D3DKMTSetGammaRamp function


## -description

The <b>D3DKMTSetGammaRamp</b> function sets the gamma ramp.

## -parameters

### -param D3DKMT_SETGAMMARAMP

*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff548307">D3DKMT_SETGAMMARAMP</a> structure that describes parameters for setting the gamma ramp.


## -returns



<b>D3DKMTSetGammaRamp</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The gamma ramp was successfully set.|
|STATUS_DEVICE_REMOVED|The graphics adapter was stopped.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
 
This function might also return other NTSTATUS values.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548307">D3DKMT_SETGAMMARAMP</a>
 

 

