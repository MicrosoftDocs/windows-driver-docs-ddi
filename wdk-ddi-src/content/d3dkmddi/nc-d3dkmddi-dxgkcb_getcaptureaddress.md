---
UID: NC:d3dkmddi.DXGKCB_GETCAPTUREADDRESS
title: DXGKCB_GETCAPTUREADDRESS (d3dkmddi.h)
description: The DxgkCbGetCaptureAddress function retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.
old-location: display\dxgkcbgetcaptureaddress.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_GETCAPTUREADDRESS callback function"]
ms.keywords: DXGKCB_GETCAPTUREADDRESS, DXGKCB_GETCAPTUREADDRESS callback, DpFunctions_a8e4882c-a196-4cdf-826f-fa4cf44ba8f8.xml, DxgkCbGetCaptureAddress, DxgkCbGetCaptureAddress callback function [Display Devices], d3dkmddi/DxgkCbGetCaptureAddress, display.dxgkcbgetcaptureaddress
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_GETCAPTUREADDRESS
 - d3dkmddi/DXGKCB_GETCAPTUREADDRESS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKCB_GETCAPTUREADDRESS
---

# DXGKCB_GETCAPTUREADDRESS callback function

## -description

**DXGKCB_GETCAPTUREADDRESS** retrieves the physical address and segment identifier of a capture buffer that is associated with the given allocation handle.

## -parameters

### -param pData [in/out]

A pointer to a [**DXGKARGCB_GETCAPTUREADDRESS**](ns-d3dkmddi-_dxgkargcb_getcaptureaddress.md) structure that describes parameters for retrieving information about a capture buffer.

## -returns

**DXGKCB_GETCAPTUREADDRESS** returns one of the following values:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_SUCCESS**           | **DXGKCB_GETCAPTUREADDRESS** successfully retrieved the capture buffer information. |
| **STATUS_INVALID_PARAMETER** | The allocation handle that is specified in the **hAllocation** member of the [DXGKARGCB_GETCAPTUREADDRESS](./ns-d3dkmddi-_dxgkargcb_getcaptureaddress.md) structure that the pData parameter pointed to was either invalid or did not represent a capture buffer. |

**DXGKCB_GETCAPTUREADDRESS** might also return other error codes that are defined in *Ntstatus.h*.

## -remarks

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, set the appropriate members of [**DXGKARGCB_GETCAPTUREADDRESS**](ns-d3dkmddi-_dxgkargcb_getcaptureaddress.md) and then call **DxgkCbGetCaptureAddress** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARGCB_GETCAPTUREADDRESS**](ns-d3dkmddi-_dxgkargcb_getcaptureaddress.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)
