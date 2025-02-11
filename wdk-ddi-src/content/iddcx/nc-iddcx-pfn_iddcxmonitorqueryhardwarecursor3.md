---
UID: NC:iddcx.PFN_IDDCXMONITORQUERYHARDWARECURSOR3
tech.root: display 
title: PFN_IDDCXMONITORQUERYHARDWARECURSOR3
ms.date: 02/10/2025
targetos: Windows
description: Learn more about the PFN_IDDCXMONITORQUERYHARDWARECURSOR3 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: iddcx.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2 September Update (IddCx version 1.10)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXMONITORQUERYHARDWARECURSOR3
f1_keywords:
 - PFN_IDDCXMONITORQUERYHARDWARECURSOR3
 - iddcx/PFN_IDDCXMONITORQUERYHARDWARECURSOR3
dev_langs:
 - c++
helpviewer_keywords:
 - PFN_IDDCXMONITORQUERYHARDWARECURSOR3
---

## -description

**PFN_IDDCXMONITORQUERYHARDWARECURSOR3** is a pointer to an OS callback function that retrieves the current hardware cursor information for the specified monitor.

## -parameters

### -param DriverGlobals

[in] Contains system-defined per-driver data.

### -param MonitorObject

[in] The monitor object that the hardware cursor information is associated with.

### -param pInArgs

[in] Input arguments of function.

### -param pOutArgs

[out] Output arguments of function.

## -returns

**PFN_IDDCXMONITORQUERYHARDWARECURSOR3** returns an NTSTATUS value that indicates the success or failure of the function.

## -remarks

An indirect display driver (IDD) shouldn't use this function pointer to directly. IDDs should instead call [**IddCxMonitorQueryHardwareCursor3**](nf-iddcx-iddcxmonitorqueryhardwarecursor3.md).

## -see-also

[**IddCxMonitorQueryHardwareCursor3**](nf-iddcx-iddcxmonitorqueryhardwarecursor3.md)
