---
UID: NS:d3dukmdt._D3DDDI_QUERYREGISTRY_FLAGS
title: D3DDDI_QUERYREGISTRY_FLAGS (d3dukmdt.h)
description: Learn about the D3DDDI_QUERYREGISTRY_FLAGS structure.
ms.date: 02/06/2025
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DDDI_QUERYREGISTRY_FLAGS
targetos: Windows
tech.root: display
f1_keywords:
 - _D3DDDI_QUERYREGISTRY_FLAGS
 - d3dukmdt/_D3DDDI_QUERYREGISTRY_FLAGS
 - D3DDDI_QUERYREGISTRY_FLAGS
 - d3dukmdt/D3DDDI_QUERYREGISTRY_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_QUERYREGISTRY_FLAGS
 - D3DDDI_QUERYREGISTRY_FLAGS
---

# D3DDDI_QUERYREGISTRY_FLAGS structure

## -description

These flags control how strings are being retrieved through [**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md) for **D3DDDI_QUERYADAPTERTYPE_QUERYREGISTRY**.

## -struct-fields

### -field TranslatePath

**TranslatePath** is meant for use by the caller from a virtual machine. This flag is ignored if a call is made from a non-virtualized environment. For more information, see [GPU para-virtualization](/windows-hardware/drivers/display/gpu-paravirtualization).

When a particular registry key stores a path to another driver file, the caller of [**pfnQueryAdapterInfoCb2**](../d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb2.md) might have that path translated into the path that an isolated processes can access. Setting **TranslatePath** to 1 indicates the registry key is a string that should be translated, when appropriate.

When this flag is set, [**D3DDDI_QUERYREGISTRY_INFO::ValueType**](ns-d3dukmdt-_d3dddi_queryregistry_info.md) must be `REG_SZ`, `REG_MULTI_SZ`, or `REG_EXPAND_SZ` and the value string is processed to translate the path to the virtual machine space. The translation only happens when the **OutputString** is an absolute path to a file in the DriverStore folder. The path is translated to `<SystemDrive>:\windows\system32\HostDriverStore\...`.

Set the flag only when **D3DDDI_QUERYREGISTRY_INFO::QueryType** is **D3DDDI_QUERYREGISTRY_SERVICEKEY** or **D3DDDI_QUERYREGISTRY_ADAPTERKEY**.

The registry string must be a full path to a file in the driver store. Translation won't occur when translation isn't needed.

**TranslatePath** must be set to 0 when [**D3DDDI_QUERYREGISTRY_INFO**](ns-d3dukmdt-_d3dddi_queryregistry_info.md)**::D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** are used.
However, **D3DDDI_QUERYREGISTRY_DRIVERSTOREPATH** and **D3DDDI_QUERYREGISTRY_DRIVERIMAGEPATH** will always act as if **TranslatePath** were set to 1.

### -field MutableValue

Reserved. Callers of **pfnQueryAdapterInfoCb2** must set this value to 0.

### -field Reserved

Reserved. Callers of **pfnQueryAdapterInfoCb2** must set this value to 0.

### Value

The **Value** field exists to read all these flags in a raw syntax, instead of the named bitfield.

## -see-also

[**D3DDDI_QUERYREGISTRY_INFO**](ns-d3dukmdt-_d3dddi_queryregistry_info.md)

[**D3DKMTQueryAdapterInfo**](../d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo.md)
