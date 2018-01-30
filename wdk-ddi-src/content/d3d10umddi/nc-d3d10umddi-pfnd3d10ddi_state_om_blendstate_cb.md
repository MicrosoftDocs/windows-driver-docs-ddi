---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_BLENDSTATE_CB
title: PFND3D10DDI_STATE_OM_BLENDSTATE_CB
author: windows-driver-content
description: The pfnStateOmBlendStateCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger blend state.
old-location: display\pfnstateomblendstatecb.htm
old-project: display
ms.assetid: 3cec9d99-0d15-4c61-9de2-ab203a56441d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnstateomblendstatecb, pfnStateOmBlendStateCb callback function [Display Devices], pfnStateOmBlendStateCb, PFND3D10DDI_STATE_OM_BLENDSTATE_CB, PFND3D10DDI_STATE_OM_BLENDSTATE_CB, d3d10umddi/pfnStateOmBlendStateCb, d3d10state_functions_18da32ca-c230-4119-a721-cbb8511a8b7c.xml
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
-	pfnStateOmBlendStateCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_OM_BLENDSTATE_CB callback


## -description


The <b>pfnStateOmBlendStateCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger blend state.


## -prototype


````
PFND3D10DDI_STATE_OM_BLENDSTATE_CB pfnStateOmBlendStateCb;

void APIENTRY pfnStateOmBlendStateCb(
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


The <b>pfnStateOmBlendStateCb</b> function calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setblendstate.md">SetBlendState</a> function with the current blend state.



## -see-also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setblendstate.md">SetBlendState</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_OM_BLENDSTATE_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

