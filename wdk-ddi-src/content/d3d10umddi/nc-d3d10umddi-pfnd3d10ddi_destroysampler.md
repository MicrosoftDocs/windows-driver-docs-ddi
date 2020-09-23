---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSAMPLER
title: PFND3D10DDI_DESTROYSAMPLER (d3d10umddi.h)
description: The DestroySampler function destroys the specified sampler object. The sampler object can be destoyed only if it is not currently bound to a display device.
old-location: display\destroysampler.htm
ms.assetid: 8e66de90-c336-43b4-b0ad-cb24cea3638c
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DESTROYSAMPLER callback function"]
ms.keywords: DestroySampler, DestroySampler callback function [Display Devices], PFND3D10DDI_DESTROYSAMPLER, PFND3D10DDI_DESTROYSAMPLER callback, UserModeDisplayDriverDx10_Functions_814d0591-6b69-4b30-9463-3c23c62e0b6a.xml, d3d10umddi/DestroySampler, display.destroysampler
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
 - PFND3D10DDI_DESTROYSAMPLER
 - d3d10umddi/PFND3D10DDI_DESTROYSAMPLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - DestroySampler
---

# PFND3D10DDI_DESTROYSAMPLER callback function


## -description

The <b>DestroySampler</b> function destroys the specified sampler object. The sampler object can be destoyed only if it is not currently bound to a display device.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hSampler* [in]

A handle to the driver's private data for the sampler object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <b>DestroySampler</b> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>