---
UID: NC:d3dumddi.PFND3DDDI_OPENADAPTER
title: PFND3DDDI_OPENADAPTER (d3dumddi.h)
description: Learn more about the PFND3DDDI_OPENADAPTER callback function.
tech.root: display
ms.date: 02/06/2025
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_OPENADAPTER
 - d3dumddi/PFND3DDDI_OPENADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_OPENADAPTER
---

# PFND3DDDI_OPENADAPTER callback function

## -description

The user-mode display driver's (UMD) **OpenAdapter** function creates a graphics adapter object that is referenced in subsequent calls.

## -parameters

### -param unnamedParam1

[in/out] *pOpenData* points to a [**D3DDDIARG_OPENADAPTER**](ns-d3dumddi-_d3dddiarg_openadapter.md) structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Direct3D runtime can use.

## -returns

**OpenAdapter** returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The graphics adapter object is successfully created.|
|E_OUTOFMEMORY|OpenAdapter could not allocate the required memory for it to complete.|

## -remarks

The graphics adapter object that is created by **OpenAdapter** represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling [**CreateDevice**](nc-d3dumddi-pfnd3dddi_createdevice.md), the UMD should call the [**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md) function to query for the graphics hardware capabilities from the kernel-mode display miniport driver (KMD).

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.

## -see-also

[**CreateDevice**](nc-d3dumddi-pfnd3dddi_createdevice.md)

[**D3DDDIARG_OPENADAPTER**](ns-d3dumddi-_d3dddiarg_openadapter.md)

[**pfnQueryAdapterInfoCb**](nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md)
