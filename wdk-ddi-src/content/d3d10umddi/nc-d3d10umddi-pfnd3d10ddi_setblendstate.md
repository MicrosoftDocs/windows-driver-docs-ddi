---
UID: NC:d3d10umddi.PFND3D10DDI_SETBLENDSTATE
title: PFND3D10DDI_SETBLENDSTATE
author: windows-driver-content
description: The SetBlendState function sets a blend state.
old-location: display\setblendstate.htm
old-project: display
ms.assetid: 8794413f-f4d5-4382-8886-2f0659d8a781
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_SETBLENDSTATE, SetBlendState, SetBlendState callback function [Display Devices], UserModeDisplayDriverDx10_Functions_11dcf032-7cd6-497e-985d-548960276981.xml, d3d10umddi/SetBlendState, display.setblendstate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	SetBlendState
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_SETBLENDSTATE callback


## -description


The <i>SetBlendState</i> function sets a blend state. 


## -prototype


````
PFND3D10DDI_SETBLENDSTATE SetBlendState;

VOID APIENTRY SetBlendState(
  _In_       D3D10DDI_HDEVICE     hDevice,
  _In_       D3D10DDI_HBLENDSTATE hState,
  _In_ const FLOAT                pBlendFactor,
  _In_       UINT                 SampleMask
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param D3D10DDI_HBLENDSTATE


### -param FLOAT[4]


### -param UINT








#### - SampleMask [in]

 A sample format mask.


#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hState [in]

 A handle to the blend state to set.


#### - pBlendFactor [in]

 A four-element array of single-precision float vectors that the driver uses to set the blend state.


## -returns



None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.




## -remarks



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetBlendState</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.




## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 


