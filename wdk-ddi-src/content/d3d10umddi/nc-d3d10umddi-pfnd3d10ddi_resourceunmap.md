---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEUNMAP
title: PFND3D10DDI_RESOURCEUNMAP (d3d10umddi.h)
description: The ResourceUnmap function unmaps a subresource of a resource.
old-location: display\resourceunmap.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_RESOURCEUNMAP callback function"]
ms.keywords: PFND3D10DDI_RESOURCEUNMAP, PFND3D10DDI_RESOURCEUNMAP callback, ResourceUnmap, ResourceUnmap callback function [Display Devices], UserModeDisplayDriverDx10_Functions_473ebdfc-f365-4194-9d52-6338e19ca0d5.xml, d3d10umddi/ResourceUnmap, display.resourceunmap
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
 - PFND3D10DDI_RESOURCEUNMAP
 - d3d10umddi/PFND3D10DDI_RESOURCEUNMAP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - ResourceUnmap
---

# PFND3D10DDI_RESOURCEUNMAP callback function


## -description

The <i>ResourceUnmap</i> function unmaps a subresource of a resource.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource* [in]

A handle to the resource to unmap.

### -param Arg3

*Subresource* [in]

An index that indicates the subresource to unmap.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver can call <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> to set the <b>D3DDDIERR_DEVICEREMOVED</b> error code; however, the driver is not required to set <b>D3DDDIERR_DEVICEREMOVED</b> if the device was removed. Calls to <b>pfnSetErrorCb</b> to set any other error code are critical.

<h3><a id="Restrictions_on_input_values"></a><a id="restrictions_on_input_values"></a><a id="RESTRICTIONS_ON_INPUT_VALUES"></a>Restrictions on input values</h3>
For Windows Display Driver Model (WDDM) 1.3 and later drivers, the Microsoft Direct3D runtime supplies a restricted set of input values used by this function. For a list of all restricted values, see [Direct3D rendering performance improvements](/windows-hardware/drivers/display/direct3d-rendering-performance-improvements).

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
