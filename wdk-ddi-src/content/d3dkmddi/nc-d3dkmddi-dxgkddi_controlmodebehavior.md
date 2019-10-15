---
UID: NC:d3dkmddi.DXGKDDI_CONTROLMODEBEHAVIOR
title: DXGKDDI_CONTROLMODEBEHAVIOR
author: windows-driver-content
description: The DxgkDdiControlModeBehavior function requests high-level mode enumeration and settings behaviors.
tech.root: display
ms.assetid: a98fa9dd-f514-4e30-8c77-71a424c1675c
ms.author: windowsdriverdev
ms.date: 10/14/2019
ms.topic: callback
req.header: d3dkmddi.h
req.include-header:
req.target-type: Desktop
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
 - apiref
api_type: 
 - UserDefined
api_location: 
 - d3dkmddi.h
api_name: 
 - DXGKDDI_CONTROLMODEBEHAVIOR
product: 
 - Windows
targetos: Windows
---

# DXGKDDI_CONTROLMODEBEHAVIOR callback function

## -description

The **DxgkDdiControlModeBehavior** function requests high-level mode enumeration and settings behaviors.

## -prototype

```cpp
//Declaration

DXGKDDI_CONTROLMODEBEHAVIOR DxgkddiControlmodebehavior;

// Definition

NTSTATUS DxgkddiControlmodebehavior
(
    IN_CONST_HANDLE hAdapter,
    INOUT_PDXGKARG_CONTROLMODEBEHAVIOR pControlModeBehaviorArg
)
{...}

```

## -parameters

### -param hAdapter

[in] Handle to the WDDM display miniport adapter being queried.

### -param pControlModeBehaviorArg

[in/out] Pointer to a [DXGKARG_CONTROLMODEBEHAVIOR](ns-d3dkmddi-_dxgkarg_controlmodebehavior.md) structure that contains the display mode behaviors that the OS is requesting from the driver as input, and the results of the request as output.

## -returns

**DxgkDdiCreateContext** returns one of the following values:

| Return code | Description |
|------------ | ----------- |
| STATUS_SUCCESS        | The request has been successfully completed. |
| STATUS_NO_MEMORY      | There is insufficient memory to complete this request. |
| STATUS_GRAPHICS_*XXX* | One of the invalid parameter codes that can be returned by the OS via DXGDDI_VIDPN* interfaces. These codes should occur only during development since they indicate a bug in the driver or OS. |

## -remarks

## -see-also

[DXGKARG_CONTROLMODEBEHAVIOR](ns-d3dkmddi-_dxgkarg_controlmodebehavior.md)
