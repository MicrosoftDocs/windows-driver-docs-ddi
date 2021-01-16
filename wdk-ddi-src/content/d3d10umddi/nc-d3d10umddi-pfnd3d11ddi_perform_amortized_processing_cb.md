---
UID: NC:d3d10umddi.PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
title: PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB (d3d10umddi.h)
description: The pfnPerformAmortizedProcessingCb function performs amortized processing.
old-location: display\pfnperformamortizedprocessingcb.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB callback function"]
ms.keywords: PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB, PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB callback, d3d10umddi/pfnPerformAmortizedProcessingCb, d3d11state_functions_7da0e622-fd33-44b6-a096-143ff6c47953.xml, display.pfnperformamortizedprocessingcb, pfnPerformAmortizedProcessingCb, pfnPerformAmortizedProcessingCb callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnPerformAmortizedProcessingCb is supported beginning with the Windows 7 operating system.
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
 - d3d10umddi/PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB
---

# PFND3D11DDI_PERFORM_AMORTIZED_PROCESSING_CB callback function


## -description

The <b>pfnPerformAmortizedProcessingCb</b> function performs amortized processing.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Microsoft Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

## -remarks

For more information about amortized processing, see <a href="/windows-hardware/drivers/display/changes-from-direct3d-10">Changes from Direct3D 10</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>

