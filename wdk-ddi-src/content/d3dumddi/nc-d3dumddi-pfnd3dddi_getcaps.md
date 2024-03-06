---
UID: NC:d3dumddi.PFND3DDDI_GETCAPS
title: PFND3DDDI_GETCAPS (d3dumddi.h)
description: The GetCaps function queries for capabilities of the graphics adapter.
old-location: display\getcaps.htm
tech.root: display
ms.date: 02/02/2022
keywords: ["PFND3DDDI_GETCAPS callback function"]
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3DDDI_GETCAPS, PFND3DDDI_GETCAPS callback, UserModeDisplayDriver_Functions_2848e873-69ef-4b77-b8bc-8ae9f4abe2c9.xml, d3dumddi/GetCaps, display.getcaps
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows Vista
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
 - PFND3DDDI_GETCAPS
 - d3dumddi/PFND3DDDI_GETCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - PFND3DDDI_GETCAPS
---

# PFND3DDDI_GETCAPS callback function

## -description

The D3D runtime calls the driver's **PFND3DDDI_GETCAPS** callback function to query the capabilities of the graphics adapter.

## -parameters

### -param hAdapter

A handle that identifies the graphics adapter.

### -param unnamedParam2

*pData* [in, out]

A pointer to a [**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md) structure that describes the capabilities to retrieve.

## -returns

**PFND3DDDI_GETCAPS** returns one of the following values:

| Return code   | Description |
| -----------   | ----------- |
| S_OK          | The capabilities were successfully retrieved.|
| E_OUTOFMEMORY | PFND3DDDI_GETCAPS could not allocate the required memory for it to complete.|

## -remarks

The data returned in the **pData** member of the [**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md) structure depends on the type of data that is requested (that is, the data depends on **D3DDDIARG_GETCAPS.Type** and sometimes on the **pInfo** member).

The following table has two examples of how to set up the **PFND3DDDI_GETCAPS** call depending on the value of [**D3DDDIARG_GETCAPS.Type**](ns-d3dumddi-_d3dddiarg_getcaps.md).

| D3DDDIARG_GETCAPS member | Example 1 | Example 2 |
|:--|:--|:--|
| **Type**     | **D3DDDICAPS_DDRAW** | **D3DDDICAPS_GETFORMATCOUNT** |
| **pInfo**    | [in] NULL (no conditions are set) | [in] NULL (no conditions are set) |
| **pData**    | [out] [**DDRAW_CAPS**](./ns-d3dumddi-_ddraw_caps.md) (unique pointer) | [out] UINT* (unique pointer) |
| **DataSize** | sizeof(DDRAW_CAPS) | sizeof(UINT) |
| Notes   | Driver must fill in the [**DDRAW_CAPS**](./ns-d3dumddi-_ddraw_caps.md) structure with the DirectDraw capabilities that it supports. | Driver must fill the buffer pointed to by **pData** with a UINT value that represents the number of [**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md) surface formats that the device supports. |

See [**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md) for explanations of other values for **D3DDDIARG_GETCAPS.Type** that are used for multiplane overlays.

### Simple_instancing

If a Direct3D Level 9 driver that supports Windows Display Driver Model (WDDM) 1.3 and later completes a call to **PFND3DDDI_GETCAPS** and returns S_OK but doesn't change the data in the [**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md) structure, it is indicating to the Direct3D runtime that the hardware and driver don't support simple instancing. For more info, see [**D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT**](ns-d3dumddi-d3dddicaps_simple_instancing_support.md).

## -see-also

[**D3DDDIARG_GETCAPS**](ns-d3dumddi-_d3dddiarg_getcaps.md)

[**D3DDDICAPS_SIMPLE_INSTANCING_SUPPORT**](ns-d3dumddi-d3dddicaps_simple_instancing_support.md)

[**D3DDDIFORMAT**](../d3dukmdt/ne-d3dukmdt-_d3dddiformat.md)

[**D3DDDI_ADAPTERFUNCS**](ns-d3dumddi-_d3dddi_adapterfuncs.md)

[**DDRAW_CAPS**](ns-d3dumddi-_ddraw_caps.md)
