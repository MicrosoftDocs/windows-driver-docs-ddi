---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_RASTSTATE_CB
title: PFND3D10DDI_STATE_RS_RASTSTATE_CB
author: windows-driver-content
description: The pfnStateRsRastStateCb function causes the Microsoft Direct3D 10 runtime to refresh the rasterization state.
old-location: display\pfnstatersraststatecb.htm
old-project: display
ms.assetid: 2ce213a6-8075-4ad9-9f58-204c2f7fd8d9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_STATE_RS_RASTSTATE_CB, d3d10state_functions_4b9543a0-e36e-4540-bccd-9d7beceaba60.xml, d3d10umddi/pfnStateRsRastStateCb, display.pfnstatersraststatecb, pfnStateRsRastStateCb, pfnStateRsRastStateCb callback function [Display Devices]
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
-	pfnStateRsRastStateCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_RS_RASTSTATE_CB callback


## -description


The <b>pfnStateRsRastStateCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the rasterization state.


## -parameters




### -param Arg1








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateRsRastStateCb</b> function calls the user-mode display driver's <a href="https://msdn.microsoft.com/8162c9c9-4ebd-45a9-adaf-576f25c3907e">SetRasterizerState</a> function with the current rasterizer state.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/8162c9c9-4ebd-45a9-adaf-576f25c3907e">SetRasterizerState</a>
 

 

