---
UID: NS:d3dumddi._D3DDDI_ADAPTERCALLBACKS
title: D3DDDI_ADAPTERCALLBACKS (d3dumddi.h)
description: Learn more about the D3DDDI_ADAPTERCALLBACKS structure.
tech.root: display
ms.date: 02/06/2025
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.typenames: D3DDDI_ADAPTERCALLBACKS
f1_keywords:
 - _D3DDDI_ADAPTERCALLBACKS
 - d3dumddi/_D3DDDI_ADAPTERCALLBACKS
 - D3DDDI_ADAPTERCALLBACKS
 - d3dumddi/D3DDDI_ADAPTERCALLBACKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDI_ADAPTERCALLBACKS
 - D3DDDI_ADAPTERCALLBACKS
---

# D3DDDI_ADAPTERCALLBACKS structure

## -description

The **D3DDDI_ADAPTERCALLBACKS** structure contains pointers to Direct3D runtime callback functions that the user-mode display driver (UMD) can use.

## -struct-fields

### -field pfnQueryAdapterInfoCb

Pointer to the [**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md) function, which UMD uses to query the display miniport driver (KMD) for adapter configuration information.

### -field pfnGetMultisampleMethodListCb

Pointer to the [**pfnGetMultisampleMethodListCb**](nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb.md) function, which UMD uses to retrieve the list of multiple-sampling methods that are used for an allocation.

### -field pfnQueryAdapterInfoCb2

Pointer to the runtime's [**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md) function, which UMD uses to query the display miniport driver (KMD) for adapter information.

## -remarks

The Direct3D runtime passes **D3DDDI_ADAPTERCALLBACKS** to UMD when it calls UMD's [**OpenAdapter**](nc-d3dumddi-pfnd3dddi_openadapter.md) function.

## -see-also

[**D3DDDIARG_OPENADAPTER**](ns-d3dumddi-_d3dddiarg_openadapter.md)

[**Openadapter**](nc-d3dumddi-pfnd3dddi_openadapter.md)

[**pfnGetMultisampleMethodListCb**](nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb.md)

[**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md)

[**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)
