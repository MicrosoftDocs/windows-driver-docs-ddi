---
UID: NC:d3dumddi.PFND3DDDI_GETMULTISAMPLEMETHODLISTCB
title: PFND3DDDI_GETMULTISAMPLEMETHODLISTCB (d3dumddi.h)
description: The pfnGetMultisampleMethodListCb function retrieves a list of multiple-sample methods that are used for the given width, height, and format of an allocation.
old-location: display\pfngetmultisamplemethodlistcb.htm
tech.root: display
ms.assetid: 2e3f9ee9-83a0-4b81-a22b-594e5bd4d046
ms.date: 05/10/2018
ms.keywords: D3Druntime_Functions_301eb3f8-0145-40dc-8aa4-6b29a6876eee.xml, PFND3DDDI_GETMULTISAMPLEMETHODLISTCB, PFND3DDDI_GETMULTISAMPLEMETHODLISTCB callback, d3dumddi/pfnGetMultisampleMethodListCb, display.pfngetmultisamplemethodlistcb, pfnGetMultisampleMethodListCb, pfnGetMultisampleMethodListCb callback function [Display Devices]
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnGetMultisampleMethodListCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnGetMultisampleMethodListCb
product:
 - Windows
---

# PFND3DDDI_GETMULTISAMPLEMETHODLISTCB callback function

## -description

The <b>pfnGetMultisampleMethodListCb</b> function retrieves a list of multiple-sample methods that are used for the given width, height, and format of an allocation.

## -parameters

### -param hAdapter

A handle to the graphics adapter object.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_getmultisamplemethodlist">D3DDDICB_GETMULTISAMPLEMETHODLIST</a> structure that describes the list of multiple-sample methods for an allocation.

## -returns

<b>pfnGetMultisampleMethodListCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The list of multiple-sample methods was successfully retrieved.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|

This function might also return other HRESULT values.

## -remarks

The user-mode display driver typically uses the <b>pfnGetMultisampleMethodListCb</b> function with its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a> function and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function. The driver uses <b>pfnGetMultisampleMethodListCb</b> when the Direct3D runtime calls the driver's <i>CreateResource</i>, <i>CreateResource(D3D10)</i>, or <i>CreateResource(D3D11)</i> to request that the driver create a multiple-sampled primary. The driver also uses <b>pfnGetMultisampleMethodListCb</b> when it must perform multiple-sampling while scanning out from the primary. This type of multiple-sampling might consume additional memory bandwidth, beyond the bandwidth required for scanning out the display mode. Therefore, <b>pfnGetMultisampleMethodListCb</b> queries the display mode manager (DMM) (and indirectly the display miniport driver) to retrieve a list of supported multiple-sampling methods for the given width, height, and format. If <b>pfnGetMultisampleMethodListCb</b> reports that no methods are supported, the user-mode display driver must use a nonscan-out version of multiple-sampling, typically by creating a standard nonmultiple-sampled primary.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_createresource">CreateResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createresource">CreateResource(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_createresource">CreateResource(D3D11)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddicb_getmultisamplemethodlist">D3DDDICB_GETMULTISAMPLEMETHODLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>

