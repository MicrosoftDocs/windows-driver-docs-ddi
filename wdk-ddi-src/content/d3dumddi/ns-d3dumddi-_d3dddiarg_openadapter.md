---
UID: NS:d3dumddi._D3DDDIARG_OPENADAPTER
title: D3DDDIARG_OPENADAPTER (d3dumddi.h)
description: Learn more about the D3DDDIARG_OPENADAPTER structure.
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
req.typenames: D3DDDIARG_OPENADAPTER
f1_keywords:
 - _D3DDDIARG_OPENADAPTER
 - d3dumddi/_D3DDDIARG_OPENADAPTER
 - D3DDDIARG_OPENADAPTER
 - d3dumddi/D3DDDIARG_OPENADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_OPENADAPTER
 - D3DDDIARG_OPENADAPTER
---

# D3DDDIARG_OPENADAPTER structure

## -description

The **D3DDDIARG_OPENADAPTER** structure contains information that describes the graphics adapter object.

## -struct-fields

### -field hAdapter [in/out]

A handle to the graphics adapter object. On input to the [**OpenAdapter**](nc-d3dumddi-pfnd3dddi_openadapter.md) function, **hAdapter** specifies the handle that the user-mode display driver (UMD) should use to query for graphics adapter capabilities when the driver calls the Direct3D runtime-supplied [**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md) callback function.

The UMD generates a unique handle and passes it back to the Direct3D runtime. On output from the [**OpenAdapter**](nc-d3dumddi-pfnd3dddi_openadapter.md) function, **hAdapter** specifies the handle that the Direct3D runtime uses in subsequent driver calls to identify the graphics adapter object.

### -field Interface [in]

The Direct3D/DirectDraw interface version (for example, 9, 10, 11, 12) that opens the graphics adapter.

### -field Version [in]

A number that the driver can use to identify when the Direct3D/DirectDraw runtime was built. For example, the driver can use the version number to differentiate between a runtime that is released with Windows Vista and a runtime that is released with a subsequent service pack, which might contain a fix that the driver requires.

### -field pAdapterCallbacks [in]

A pointer to a [**D3DDDI_ADAPTERCALLBACKS**](ns-d3dumddi-_d3dddi_adaptercallbacks.md) structure that contains the Direct3D runtime-supplied callback functions that the driver can use, including:

* [**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md)
* [**pfnGetMultisampleMethodListCb**](nc-d3dumddi-pfnd3dddi_getmultisamplemethodlistcb.md)
* [**pfnQueryAdapterInfoCb2**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md)

### -field pAdapterFuncs [out]

A pointer to a [**D3DDDI_ADAPTERFUNCS**](ns-d3dumddi-_d3dddi_adapterfuncs.md) structure that contains a table of UMD adapter-specific functions. The Direct3D runtime uses these functions to communicate with the UMD about operations that are specific to the graphics adapter.

### -field DriverVersion [out]

The version of the Direct3D UMD's interface, which was obtained from the *D3dumddi.h* header file, that the driver was compiled with. The UMD should return D3D_UMD_INTERFACE_VERSION.

## -see-also

[**D3DDDI_ADAPTERCALLBACKS**](ns-d3dumddi-_d3dddi_adaptercallbacks.md)

[**D3DDDI_ADAPTERFUNCS**](ns-d3dumddi-_d3dddi_adapterfuncs.md)

[**OpenAdapter**](nc-d3dumddi-pfnd3dddi_openadapter.md)

[**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md)
