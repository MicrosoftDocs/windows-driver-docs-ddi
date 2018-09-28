---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_CONSTBUF_CB
title: PFND3D10DDI_STATE_PS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStatePsConstBufCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound constant buffers.
old-location: display\pfnstatepsconstbufcb.htm
ms.assetid: f4670f69-5154-4f6b-ba98-2b91a16e7b2f
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D10DDI_STATE_PS_CONSTBUF_CB, PFND3D10DDI_STATE_PS_CONSTBUF_CB callback, d3d10state_functions_edcff973-6c62-4cd9-a21f-c40a6afd9548.xml, d3d10umddi/pfnStatePsConstBufCb, display.pfnstatepsconstbufcb, pfnStatePsConstBufCb, pfnStatePsConstBufCb callback function [Display Devices]
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
-	pfnStatePsConstBufCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_PS_CONSTBUF_CB callback function


## -description


The <b>pfnStatePsConstBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound constant buffers.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function.

### -param Arg2

*Count* [in]

The total number of buffers to refresh. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value. 

### -param Arg3

*Base* [in]

The starting constant buffer to refresh. 


## -returns



None




## -remarks



The <i>Base</i> and <i>Count</i> parameters that the driver passes to the <b>pfnStatePsConstBufCb</b> function directly correspond to the <i>StartBuffer</i> and <i>NumBuffers</i> parameters that are passed to the driver's <a href="https://msdn.microsoft.com/d77070d8-daf8-44d3-9032-a7a7d3c2c242">PsSetConstantBuffers</a> function.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/d77070d8-daf8-44d3-9032-a7a7d3c2c242">PsSetConstantBuffers</a>
 

 

