---
UID: NC:d3d10umddi.PFND3D10DDI_CREATESAMPLER
title: PFND3D10DDI_CREATESAMPLER (d3d10umddi.h)
description: The CreateSampler function creates a sampler.
old-location: display\createsampler.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_CREATESAMPLER callback function"]
ms.keywords: CreateSampler, CreateSampler callback function [Display Devices], PFND3D10DDI_CREATESAMPLER, PFND3D10DDI_CREATESAMPLER callback, UserModeDisplayDriverDx10_Functions_16c89dca-e337-42c7-a666-f0f4c9a6d3e3.xml, d3d10umddi/CreateSampler, display.createsampler
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_CREATESAMPLER
 - d3d10umddi/PFND3D10DDI_CREATESAMPLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - CreateSampler
---

# PFND3D10DDI_CREATESAMPLER callback function


## -description

The <b>CreateSampler</b> function creates a sampler.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pSamplerDesc* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_sampler_desc">D3D10_DDI_SAMPLER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a sampler.

### -param Arg3

*hSampler* [in]

A handle to the driver's private data for the sampler. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize">CalcPrivateSamplerSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its sampler object.

### -param Arg4

*hRTSampler* [in]

A handle to the sampler that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroysampler">DestroySampler</a> function to destroy the handle that the <i>hSampler</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of sampler objects on a device at a time.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize">CalcPrivateSamplerSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10_ddi_sampler_desc">D3D10_DDI_SAMPLER_DESC</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroysampler">DestroySampler</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
