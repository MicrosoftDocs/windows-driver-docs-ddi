---
UID: NC:iddcx.PFN_IDDCXREPORTCRITICALERROR
title: PFN_IDDCXREPORTCRITICALERROR (iddcx.h)
description: PFN_IDDCXREPORTCRITICALERROR is a pointer to an OS callback function through which to report a critical error.
tech.root: display
ms.date: 09/24/2020
keywords: ["PFN_IDDCXREPORTCRITICALERROR callback function"]
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
f1_keywords:
 - PFN_IDDCXREPORTCRITICALERROR
 - iddcx/PFN_IDDCXREPORTCRITICALERROR
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - iddcx.h
api_name:
 - PFN_IDDCXREPORTCRITICALERROR
product:
 - Windows
---

# PFN_IDDCXREPORTCRITICALERROR callback function

## -description

**PFN_IDDCXREPORTCRITICALERROR** is a pointer to an OS callback function through which to report a critical error.

## -parameters

### -param DriverGlobals

[in] Pointer to an [**IDD_DRIVER_GLOBALS**](./ns-iddcx-idd_driver_globals.md) structure containing system-defined per-driver data.

### -param AdapterObject

[in, opt] The adapter object of the adapter on which the critical error occurred. If the error occurred before an IDDCX_ADAPTER object was created, pass in ```nullptr``` for this value.

### -param pInArgs

[in] Pointer to an [**IDARG_IN_REPORTCRITICALERROR**](ns-iddcx-idarg_in_reportcriticalerror.md) structure containing input arguments to the function.

## -returns

If the routine succeeds, it never returns to the driver as the driver process will be terminated.

## -remarks

An indirect display driver (IDD) should not use this pointer to directly call the function that it points to. IDDs should instead call [**IddCxReportCriticalError**](nf-iddcx-iddcxreportcriticalerror.md) to report a critical error.

## -see-also

[**IDARG_IN_REPORTCRITICALERROR**](ns-iddcx-idarg_in_reportcriticalerror.md)

[**IddCxReportCriticalError**](nf-iddcx-iddcxreportcriticalerror.md)
