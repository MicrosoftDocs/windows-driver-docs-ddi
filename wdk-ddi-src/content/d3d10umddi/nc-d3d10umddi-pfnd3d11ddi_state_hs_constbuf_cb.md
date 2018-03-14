---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_HS_CONSTBUF_CB
title: PFND3D11DDI_STATE_HS_CONSTBUF_CB
author: windows-driver-content
description: The pfnStateHsConstBufCb function causes the Microsoft Direct3D 11 runtime to refresh the hull shader constant buffer state.
old-location: display\pfnstatehsconstbufcb.htm
old-project: display
ms.assetid: 2f817497-7334-47ef-aa9d-d43386aa4751
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_STATE_HS_CONSTBUF_CB, d3d10umddi/pfnStateHsConstBufCb, d3d11state_functions_a6869e87-887a-43de-ae5e-8ca310193939.xml, display.pfnstatehsconstbufcb, pfnStateHsConstBufCb, pfnStateHsConstBufCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateHsConstBufCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateHsConstBufCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_HS_CONSTBUF_CB callback


## -description


The <b>pfnStateHsConstBufCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the hull shader constant buffer state. 


## -prototype


````
PFND3D11DDI_STATE_HS_CONSTBUF_CB pfnStateHsConstBufCb;

void APIENTRY pfnStateHsConstBufCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice,
  _In_ UINT                  Base,
  _In_ UINT                  Count
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER


### -param UINT








#### - Base [in]

 The beginning constant buffer for which the runtime should refresh state. 


#### - Count [in]

 The total number of constant buffers. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.


#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 


