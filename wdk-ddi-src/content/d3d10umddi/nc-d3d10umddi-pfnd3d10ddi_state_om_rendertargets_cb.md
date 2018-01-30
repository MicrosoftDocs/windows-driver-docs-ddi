---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_RENDERTARGETS_CB
title: PFND3D10DDI_STATE_OM_RENDERTARGETS_CB
author: windows-driver-content
description: The pfnStateOmRenderTargetsCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.
old-location: display\pfnstateomrendertargetscb.htm
old-project: display
ms.assetid: d17cd31d-44a1-4f7d-82be-1201c0d5769f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnstateomrendertargetscb, pfnStateOmRenderTargetsCb callback function [Display Devices], pfnStateOmRenderTargetsCb, PFND3D10DDI_STATE_OM_RENDERTARGETS_CB, PFND3D10DDI_STATE_OM_RENDERTARGETS_CB, d3d10umddi/pfnStateOmRenderTargetsCb, d3d10state_functions_d1d161af-c985-4d8d-b734-7acda03b13ce.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnStateOmRenderTargetsCb
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D10DDI_STATE_OM_RENDERTARGETS_CB callback


## -description


The <b>pfnStateOmRenderTargetsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.


## -prototype


````
PFND3D10DDI_STATE_OM_RENDERTARGETS_CB pfnStateOmRenderTargetsCb;

void APIENTRY pfnStateOmRenderTargetsCb(
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


The <b>pfnStateOmRenderTargetsCb</b> function calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrendertargets.md">SetRenderTargets</a> function with all of the currently set render target surfaces.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setrendertargets.md">SetRenderTargets</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_OM_RENDERTARGETS_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

