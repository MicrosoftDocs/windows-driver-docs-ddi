---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_SO_TARGETS_CB
title: PFND3D10DDI_STATE_SO_TARGETS_CB
author: windows-driver-content
description: The pfnStateSoTargetsCb function causes the Microsoft Direct3D 10 runtime to refresh the stream-out targets.
old-location: display\pfnstatesotargetscb.htm
old-project: display
ms.assetid: 9000543b-00ab-4378-9fa5-d4fc7cb05b24
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_STATE_SO_TARGETS_CB, d3d10state_functions_2e8ad85a-3bec-41cd-9d43-40b98ffd0e9e.xml, d3d10umddi/pfnStateSoTargetsCb, display.pfnstatesotargetscb, pfnStateSoTargetsCb, pfnStateSoTargetsCb callback function [Display Devices]
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
-	pfnStateSoTargetsCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_SO_TARGETS_CB callback


## -description


The <b>pfnStateSoTargetsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the stream-out targets.


## -prototype


````
PFND3D10DDI_STATE_SO_TARGETS_CB pfnStateSoTargetsCb;

void APIENTRY pfnStateSoTargetsCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateSoTargetsCb</b> function calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_so_settargets.md">SoSetTargets</a> function with all of the currently set stream-output buffers.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_so_settargets.md">SoSetTargets</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 


