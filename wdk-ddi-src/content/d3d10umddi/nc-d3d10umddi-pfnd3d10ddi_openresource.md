---
UID: NC:d3d10umddi.PFND3D10DDI_OPENRESOURCE
title: PFND3D10DDI_OPENRESOURCE (d3d10umddi.h)
description: The OpenResource(D3D10) function opens a shared resource.
old-location: display\openresource_d3d10_.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_OPENRESOURCE callback function"]
ms.keywords: OpenResource, OpenResource callback function [Display Devices], PFND3D10DDI_OPENRESOURCE, PFND3D10DDI_OPENRESOURCE callback, UserModeDisplayDriverDx10_Functions_ea9696b9-fb0f-4feb-be35-db3e59c74b4e.xml, d3d10umddi/OpenResource, display.openresource_d3d10_
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
 - PFND3D10DDI_OPENRESOURCE
 - d3d10umddi/PFND3D10DDI_OPENRESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_OPENRESOURCE
product:
 - Windows
---

# PFND3D10DDI_OPENRESOURCE callback function


## -description

The <i>OpenResource(D3D10)</i> function opens a shared resource.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pOpenResource* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openresource">D3D10DDIARG_OPENRESOURCE</a> structure that describes the parameters that the user-mode display driver uses to open a shared resource.

### -param Arg3

*hResource* [in]

A handle to the driver's private data for the resource.

### -param Arg4

*hRTResource* [in]

A handle to the resource that the driver should use anytime it calls back into the Direct3D runtime.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a> function to destroy the handle that the <i>hResource</i> parameter specifies.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivateopenedresourcesize">CalcPrivateOpenedResourceSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_createresource">D3D10DDIARG_CREATERESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddiarg_openresource">D3D10DDIARG_OPENRESOURCE</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_destroyresource">DestroyResource(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>

