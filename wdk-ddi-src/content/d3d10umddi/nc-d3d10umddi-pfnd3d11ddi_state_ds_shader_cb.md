---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SHADER_CB
title: PFND3D11DDI_STATE_DS_SHADER_CB
author: windows-driver-content
description: The pfnStateDsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.
old-location: display\pfnstatedsshadercb.htm
old-project: display
ms.assetid: 3b50f462-667e-4772-89bb-32d01e1bb7fc
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D11DDI_STATE_DS_SHADER_CB, d3d10umddi/pfnStateDsShaderCb, d3d11state_functions_5ab17831-b238-4b96-89bf-84c658463597.xml, display.pfnstatedsshadercb, pfnStateDsShaderCb, pfnStateDsShaderCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsShaderCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateDsShaderCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_DS_SHADER_CB callback


## -description


The <b>pfnStateDsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.


## -prototype


````
PFND3D11DDI_STATE_DS_SHADER_CB pfnStateDsShaderCb;

void APIENTRY pfnStateDsShaderCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_STATE_DS_SHADER_CB callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

