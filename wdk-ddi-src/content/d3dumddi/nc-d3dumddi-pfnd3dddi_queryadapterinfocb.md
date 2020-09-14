---
UID: NC:d3dumddi.PFND3DDDI_QUERYADAPTERINFOCB
title: PFND3DDDI_QUERYADAPTERINFOCB (d3dumddi.h)
description: The pfnQueryAdapterInfoCb function retrieves graphics adapter information.
old-location: display\pfnqueryadapterinfocb.htm
tech.root: display
ms.assetid: 8008574f-a89e-4fed-b745-7cf5baa68e64
ms.date: 05/10/2018
keywords: ["PFND3DDDI_QUERYADAPTERINFOCB callback function"]
ms.keywords: D3Druntime_Functions_ca5c02c9-ad59-4a10-8cb7-92d815cd6856.xml, PFND3DDDI_QUERYADAPTERINFOCB, PFND3DDDI_QUERYADAPTERINFOCB callback, d3dumddi/pfnQueryAdapterInfoCb, display.pfnqueryadapterinfocb, pfnQueryAdapterInfoCb, pfnQueryAdapterInfoCb callback function [Display Devices]
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
 - PFND3DDDI_QUERYADAPTERINFOCB
 - d3dumddi/PFND3DDDI_QUERYADAPTERINFOCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnQueryAdapterInfoCb
product:
 - Windows
---

# PFND3DDDI_QUERYADAPTERINFOCB callback function


## -description

The <b>pfnQueryAdapterInfoCb</b> function retrieves graphics adapter information.

## -parameters

### -param hAdapter

A handle to the graphics adapter object.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryadapterinfo">D3DDDICB_QUERYADAPTERINFO</a> structure that receives information about the graphics hardware.

## -returns

<b>pfnQueryAdapterInfoCb</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|Information was successfully retrieved.|
|E_INVALIDARG|Parameters were validated and determined to be incorrect.|


This function might also return other HRESULT values.

## -remarks

Before the Microsoft Direct3D runtime calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function to create the graphics context, the user-mode display driver should call <b>pfnQueryAdapterInfoCb</b> to retrieve information about the graphics hardware. This order is especially important for a multiple-monitor system. 

In the <b>pfnQueryAdapterInfoCb</b> call, the user-mode display driver sends a buffer that the display miniport driver fills with configuration data. After receiving this configuration data, the user-mode display driver can accurately report its capabilities when the runtime calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a> and GetCaps(D3D10_2) functions. When the runtime subsequently calls other user-mode display driver functions that are specified in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a> structure, the user-mode display driver can generate command streams that the hardware can process. 


#### Examples

The following code example shows how to retrieve graphics adapter information.

```cpp
    HRESULT hr;
    // Query for GART segment support
    D3DDDICB_QUERYADAPTERINFO   ddiQueryAdapterInfo;

    memset(&R200AdapterInfo, 0, sizeof(R200AdapterInfo));

    ddiQueryAdapterInfo.pPrivateDriverData = &R200AdapterInfo;
    ddiQueryAdapterInfo.PrivateDriverDataSize = sizeof(R200AdapterInfo);

    hr = m_Callbacks.pfnQueryAdapterInfoCb(m_hAdapter, &ddiQueryAdapterInfo);
    if (FAILED(hr)) {
        return FALSE;
    }

    m_ulGartSupported = R200AdapterInfo.ulGartSupported;
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_createdevice">CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_queryadapterinfo">D3DDDICB_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_adaptercallbacks">D3DDDI_ADAPTERCALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_getcaps">GetCaps</a>

