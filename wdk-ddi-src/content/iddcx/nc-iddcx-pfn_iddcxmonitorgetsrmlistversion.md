---
UID: NC:iddcx.PFN_IDDCXMONITORGETSRMLISTVERSION
title: PFN_IDDCXMONITORGETSRMLISTVERSION (iddcx.h)
description: PFN_IDDCXMONITORGETSRMLISTVERSION is a pointer to a system-implemented function that retrieves the latest SRM list version stored by the GPU.
tech.root: display
ms.assetid: f73e9f90-0f6e-40e0-9716-b184ac90c4e7
ms.date: 10/02/2020
keywords: ["PFN_IDDCXMONITORGETSRMLISTVERSION callback function"]
req.header: iddcx.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10
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
 - PFN_IDDCXMONITORGETSRMLISTVERSION
 - iddcx/PFN_IDDCXMONITORGETSRMLISTVERSION
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXMONITORGETSRMLISTVERSION
product:
 - Windows
---

# *PFN_IDDCXMONITORGETSRMLISTVERSION callback function

## -description

**PFN_IDDCXMONITORGETSRMLISTVERSION** is a pointer to a system-implemented function that retrieves the latest System Renewability Message (SRM) list version stored by the GPU.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param MonitorObject

[in] The monitor object that the SRM list is associated with.

### -param pInArgs

[in] Input arguments of the function.

### -param pOutArgs

[out] Output arguments of function.

## -returns

Returns NTSTATUS with the following error codes:

| Return value | Description |
| --- | --- |
| STATUS_SUCCESS | The routine succeeded. |
| STATUS_GRAPHICS_OPM_NOT_SUPPORTED | The GPU driver does not support this new functionality. |
| STATUS_NO_DATA_DETECTED | The GPU does not have a current SRM list. |
| STATUS_BUFFER_TOO_SMALL | The passed in buffer is too small. |

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md).

## -see-also

[**IddCxMonitorGetSrmListVersion**](nf-iddcx-iddcxmonitorgetsrmlistversion.md)
