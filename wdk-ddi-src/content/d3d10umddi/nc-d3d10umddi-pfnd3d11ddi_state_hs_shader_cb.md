---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_HS_SHADER_CB
title: PFND3D11DDI_STATE_HS_SHADER_CB
author: windows-driver-content
description: The pfnStateHsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the hull shader.
old-location: display\pfnstatehsshadercb.htm
old-project: display
ms.assetid: 74b243a2-722b-4eec-b382-936a6f2f990e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_STATE_HS_SHADER_CB, d3d10umddi/pfnStateHsShaderCb, d3d11state_functions_b16162bf-d379-49de-bc4a-85d7df7e95bf.xml, display.pfnstatehsshadercb, pfnStateHsShaderCb, pfnStateHsShaderCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateHsShaderCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateHsShaderCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_HS_SHADER_CB callback


## -description


The <b>pfnStateHsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the hull shader.


## -parameters




### -param Arg1








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

