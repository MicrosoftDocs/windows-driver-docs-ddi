---
UID: NC:d3d10umddi.PFND3D11DDI_QUERYDESIREDMODE1
tech.root: display
title: PFND3D11DDI_QUERYDESIREDMODE1
ms.date: 08/28/2024
targetos: Windows
description: Learn more about the PFND3D11DDI_QUERYDESIREDMODE1 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_QUERYDESIREDMODE1
f1_keywords:
 - PFND3D11DDI_QUERYDESIREDMODE1
 - d3d10umddi/PFND3D11DDI_QUERYDESIREDMODE1
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D11DDI_QUERYDESIREDMODE1
---

## -description

The **PFND3D11DDI_QUERYDESIREDMODE1** function is reserved for system use.

## -parameters

### -param unnamedParam1

[in] Pointer to a [**PFND3DDDI_ESCAPECB**](..//d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md) function that is a callback to the kernel-mode driver (KMD). UMD can use this pointer to call into their KMD to help inform them of the mode to choose.

### -param unnamedParam2

[in] Kernel-mode adapter handle to pass to **PFND3DDDI_ESCAPECB**

### -param unnamedParam3

[out] Pointer to a [**D3D11_UMD_MODE**](../d3d10umddi/ne-d3d10umddi-d3d11_umd_mode.md) enumeration that specifies the mode that the UMD wants to run in.

## -returns

This function is reserved for system use and the Direct3D runtime shouldn't be expected to call it. When enabled, this function queries the D3D11on12 mode that a D3D11 user-mode driver (UMD) wants to run in.

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

For more information, see [D3D11On12 open source code](https://github.com/microsoft/D3D11On12).

## -see-also

[**D3D11_UMD_MODE**](../d3d10umddi/ne-d3d10umddi-d3d11_umd_mode.md)

[**PFND3DDDI_ESCAPECB**](..//d3dumddi/nc-d3dumddi-pfnd3dddi_escapecb.md)
