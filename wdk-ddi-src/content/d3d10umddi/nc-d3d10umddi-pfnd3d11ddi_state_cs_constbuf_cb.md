---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_CS_CONSTBUF_CB
title: PFND3D11DDI_STATE_CS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStateCsConstBufCb function causes the Microsoft Direct3D 11 runtime to refresh the compute shader constant buffer state.
old-location: display\pfnstatecsconstbufcb.htm
old-project: display
ms.assetid: 13eeceff-e19e-4653-b29d-87567e486c28
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_STATE_CS_CONSTBUF_CB, d3d10umddi/pfnStateCsConstBufCb, d3d11state_functions_05ec091d-7ac4-4a5c-9ae9-d782e01cb7e9.xml, display.pfnstatecsconstbufcb, pfnStateCsConstBufCb, pfnStateCsConstBufCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateCsConstBufCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateCsConstBufCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_CS_CONSTBUF_CB callback


## -description


The <b>pfnStateCsConstBufCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the compute shader constant buffer state. 


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - Base [in]

 The beginning constant buffer for which the runtime should refresh state. 


#### - Count [in]

 The total number of constant buffers. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.


#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

