---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_CS_SHADER_CB
title: PFND3D11DDI_STATE_CS_SHADER_CB
author: windows-driver-content
description: The pfnStateCsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the compute shader.
old-location: display\pfnstatecsshadercb.htm
old-project: display
ms.assetid: ae06ffb3-3ed5-4117-8373-e41a45be37d1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PFND3D11DDI_STATE_CS_SHADER_CB, d3d10umddi/pfnStateCsShaderCb, d3d11state_functions_8292f8aa-d925-4dc9-9d9c-ccbe10d7e15f.xml, display.pfnstatecsshadercb, pfnStateCsShaderCb, pfnStateCsShaderCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateCsShaderCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateCsShaderCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_CS_SHADER_CB callback


## -description


The <b>pfnStateCsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the compute shader.


## -prototype


````
PFND3D11DDI_STATE_CS_SHADER_CB pfnStateCsShaderCb;

void APIENTRY pfnStateCsShaderCb(
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_STATE_CS_SHADER_CB callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

