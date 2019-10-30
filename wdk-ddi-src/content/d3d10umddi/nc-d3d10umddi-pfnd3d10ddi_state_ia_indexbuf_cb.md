---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_IA_INDEXBUF_CB
title: PFND3D10DDI_STATE_IA_INDEXBUF_CB (d3d10umddi.h)
description: The pfnStateIaIndexBufCb function causes the Microsoft Direct3D 10 runtime to refresh the index buffer state.
old-location: display\pfnstateiaindexbufcb.htm
ms.assetid: 3925bf83-1900-4d88-8100-1ecaa952dead
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_IA_INDEXBUF_CB, PFND3D10DDI_STATE_IA_INDEXBUF_CB callback, d3d10state_functions_0bf4b875-3cd1-4a62-a8b5-4dd61259188b.xml, d3d10umddi/pfnStateIaIndexBufCb, display.pfnstateiaindexbufcb, pfnStateIaIndexBufCb, pfnStateIaIndexBufCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnStateIaIndexBufCb"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnStateIaIndexBufCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_IA_INDEXBUF_CB callback function


## -description


The <b>pfnStateIaIndexBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the index buffer state.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

