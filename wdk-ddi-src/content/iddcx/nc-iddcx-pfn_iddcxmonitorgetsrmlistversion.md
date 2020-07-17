---
UID: NC:iddcx.PFN_IDDCXMONITORGETSRMLISTVERSION
title: PFN_IDDCXMONITORGETSRMLISTVERSION (iddcx.h)
description: Implemented by the client driver to retrieve the latest SRM list version stored by the GPU.
ms.assetid: f73e9f90-0f6e-40e0-9716-b184ac90c4e7
ms.date: 10/19/2018
keywords: ["PFN_IDDCXMONITORGETSRMLISTVERSION callback function"]
f1_keywords:
 - "iddcx/PFN_IDDCXMONITORGETSRMLISTVERSION"
 - "PFN_IDDCXMONITORGETSRMLISTVERSION"
req.header: iddcx.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
targetos: Windows
tech.root: display
---

# *PFN_IDDCXMONITORGETSRMLISTVERSION callback function

## -description

Implemented by the client driver to retrieve the latest SRM list version stored by the GPU.

## -prototype

```cpp
//Declaration

*PFN_IDDCXMONITORGETSRMLISTVERSION *PfnIddcxmonitorgetsrmlistversion;

// Definition

NTSTATUS *PfnIddcxmonitorgetsrmlistversion
(
	PIDD_DRIVER_GLOBALS DriverGlobals
	IDDCX_MONITOR MonitorObject
	CONST IDARG_IN_GETSRMLISTVERSION *pInArgs
	IDARG_OUT_GETSRMLISTVERSION *pOutArgs
)
{...}

*PFN_IDDCXMONITORGETSRMLISTVERSION


```

## -parameters

### -param DriverGlobals [in]

Contains system-defined per-driver data.

### -param MonitorObject [in]

The monitor object that the SRM list is associated with.

### -param pInArgs [in]

Input arguments of the function.

### -param pOutArgs [out]

Output arguments of function.

## -returns

Returns NTSTATUS with the following error codes:

| Return value | Description |
| --- | --- |
| STATUS_SUCCESS | The routine succeeded. |
| STATUS_GRAPHICS_OPM_NOT_SUPPORTED | The GPU driver does not support this new functionality. |
| STATUS_NO_DATA_DETECTED | The GPU does not have a current SRM list. |
| STATUS_BUFFER_TOO_SMALL | The passed in buffer is too small. |


## -remarks

Register your implementation of this callback function by setting the appropriate member of IDARG_IN_GETSRMLISTVERSION and then calling IddCxMonitorGetSrmListVersion.


## -see-also
