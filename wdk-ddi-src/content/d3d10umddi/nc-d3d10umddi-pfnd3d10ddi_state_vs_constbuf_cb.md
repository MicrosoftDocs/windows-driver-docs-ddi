---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_VS_CONSTBUF_CB
title: PFND3D10DDI_STATE_VS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStateVsConstBufCb function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound constant buffers.
old-location: display\pfnstatevsconstbufcb.htm
old-project: display
ms.assetid: 43aa7188-d6aa-4890-8eac-1342a984005b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_STATE_VS_CONSTBUF_CB, d3d10state_functions_e0f1c7e6-7f55-462a-b723-011f6bf30906.xml, d3d10umddi/pfnStateVsConstBufCb, display.pfnstatevsconstbufcb, pfnStateVsConstBufCb, pfnStateVsConstBufCb callback function [Display Devices]
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
-	pfnStateVsConstBufCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_VS_CONSTBUF_CB callback


## -description


The <b>pfnStateVsConstBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound constant buffers.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3








#### - Base [in]

 The starting constant buffer to refresh. 


#### - Count [in]

 The total number of buffers to refresh. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.


#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <i>Base</i> and <i>Count</i> parameters that the driver passes to the <b>pfnStateVsConstBufCb</b> function directly correspond to the <i>StartBuffer</i> and <i>NumBuffers</i> parameters that are passed to the driver's <a href="https://msdn.microsoft.com/38a27fa3-905a-4ab7-b018-53ea3c589661">VsSetConstantBuffers</a> function.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/38a27fa3-905a-4ab7-b018-53ea3c589661">VsSetConstantBuffers</a>
 

 

