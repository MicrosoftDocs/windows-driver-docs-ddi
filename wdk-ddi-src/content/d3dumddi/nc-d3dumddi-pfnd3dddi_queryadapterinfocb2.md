---
UID: NC:d3dumddi.PFND3DDDI_QUERYADAPTERINFOCB2
title: PFND3DDDI_QUERYADAPTERINFOCB2 (d3dumddi.h)
description: Learn more about the PFND3DDDI_QUERYADAPTERINFOCB2 callback function.
ms.date: 02/06/2025
req.header: d3dumddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3DDDI_QUERYADAPTERINFOCB2
 - d3dumddi/PFND3DDDI_QUERYADAPTERINFOCB2
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_QUERYADAPTERINFOCB2
---

# PFND3DDDI_QUERYADAPTERINFOCB2 callback function

## -description

A user-mode display driver (UMD) can call the Direct3D runtime's **pfnQueryAdapterInfoCb2** callback to retrieve information about the adapter.

## -parameters

### -param hAdapter

[in] A handle to the graphics adapter object.

### -param unnamedParam2

[in/out] Pointer to a [**D3DDDICB_QUERYADAPTERINFO2**](ns-d3dumddi-_d3dddicb_queryadapterinfo2.md) structure that receives information about the graphics hardware.

## -returns

**pfnQueryAdapterInfoCb2** returns S_OK if it successfully retrieves the information. Otherwise, it returns an error code such as the following:

| Error code | Description |
|--|--|
| E_INVALIDARG | Parameters were validated and determined to be incorrect.|

## -see-also

[**D3DDDI_ADAPTERCALLBACKS**](ns-d3dumddi-_d3dddi_adaptercallbacks.md)
