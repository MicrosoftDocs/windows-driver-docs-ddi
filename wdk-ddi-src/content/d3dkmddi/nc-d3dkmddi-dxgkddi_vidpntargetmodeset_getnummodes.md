---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
title: DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES (d3dkmddi.h)
description: The pfnGetNumModes function returns the number of target modes in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfngetnummodes.htm
ms.assetid: 1197989a-c76e-4dee-a1c7-677b6558677c
ms.date: 05/10/2018
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES, DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback, VidPnFunctions_f2fa9ea6-6ce7-485d-bcd2-b3c340ca66fc.xml, d3dkmddi/pfnGetNumModes, display.dxgk_vidpntargetmodeset_interface_pfngetnummodes, pfnGetNumModes, pfnGetNumModes callback function [Display Devices]
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetNumModes
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback function


## -description


The <b>pfnGetNumModes</b> function returns the number of target modes in a specified VidPN target mode set.


## -parameters




### -param hVidPnTargetModeSet [in]

A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/1b91c472-21eb-4aa8-91e3-c9eb70556d9f">pfnAcquireTargetModeSet</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.


### -param pNumTargetModes [out]

A pointer to a SIZE_T-typed variable that receives the number of target modes in the set.


## -returns



The <b>pfnGetNumModes</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|


## -remarks



The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>. 




## -see-also




<a href="https://msdn.microsoft.com/64a1a8f4-afbc-4337-b809-9346c1171e0b">pfnAcquireFirstModeInfo</a>



<a href="https://msdn.microsoft.com/894d0d15-d12a-4138-9a92-8f930c12dd52">pfnAcquireNextModeInfo</a>
 

 

