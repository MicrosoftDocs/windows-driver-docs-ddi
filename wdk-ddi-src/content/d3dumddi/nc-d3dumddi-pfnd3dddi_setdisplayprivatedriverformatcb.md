---
UID: NC:d3dumddi.PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB
title: PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB (d3dumddi.h)
description: The pfnSetDisplayPrivateDriverFormatCb function changes the private-format attribute of a video present source.
old-location: display\pfnsetdisplayprivatedriverformatcb.htm
tech.root: display
ms.assetid: 499e6de7-67cc-4834-bcec-4f3907b180f7
ms.date: 05/10/2018
keywords: ["PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB callback function"]
ms.keywords: D3Druntime_Functions_36bd86e3-96bb-4c68-85a1-a678a54daed4.xml, PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB, PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB callback, d3dumddi/pfnSetDisplayPrivateDriverFormatCb, display.pfnsetdisplayprivatedriverformatcb, pfnSetDisplayPrivateDriverFormatCb, pfnSetDisplayPrivateDriverFormatCb callback function [Display Devices]
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
 - PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB
 - d3dumddi/PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnSetDisplayPrivateDriverFormatCb
product:
 - Windows
---

# PFND3DDDI_SETDISPLAYPRIVATEDRIVERFORMATCB callback function


## -description

The <b>pfnSetDisplayPrivateDriverFormatCb</b> function changes the private-format attribute of a video present source.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_setdisplayprivatedriverformat">D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that describes how to format a video present source.

## -returns

<b>pfnSetDisplayPrivateDriverFormatCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The video present source was successfully changed.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|
|E_FAIL|pfnSetDisplayPrivateDriverFormatCb could not change the private-format attribute of the video present source.|

This function might also return other HRESULT values.

## -remarks

Changing the private-format attribute of a video present source is useful to accommodate a full-screen DirectX application that creates its flipping change when the shared GDI primary surface is in a non-optimal private format for the full-screen DirectX application. For example, suppose the display miniport driver always creates the GDI shared primary surface as un-swizzled. However, for performance reasons, the user-mode display driver requires that all the surfaces in a full-screen flipping chain are swizzled. The user-mode display driver could then create the back buffers as swizzled and call <b>pfnSetDisplayPrivateDriverFormatCb</b> to change the shared GDI primary surface to swizzled.

If the call to <b>pfnSetDisplayPrivateDriverFormatCb</b> fails, the user-mode display driver should continue without changing the private-format attribute of the video present source. In the preceding example, the driver can either leave the shared primary as un-swizzled and have the back buffers swizzled or the driver can change the back buffers to the un-swizzled format.

If the user-mode display driver receives the D3DDDIERR_INCOMPATIBLEPRIVATEFORMAT error from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplaymodecb">pfnSetDisplayModeCb</a> function, the driver can do one of the following:

<ul>
<li>
Change the private-format attribute of the primary surface and call <b>pfnSetDisplayModeCb</b> again.

</li>
<li>
Call <b>pfnSetDisplayPrivateDriverFormatCb</b> and attempt to change the private-format attribute of the video present source. The driver can then call <b>pfnSetDisplayModeCb</b> again. 

</li>
</ul>
The user-mode display driver can call <b>pfnSetDisplayPrivateDriverFormatCb</b> only if the <b>Version</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure was set to greater than seven when the display device (specified by the <i>hDevice</i> parameter) was created in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a> function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_setdisplayprivatedriverformat">D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_setdisplaymodecb">pfnSetDisplayModeCb</a>

