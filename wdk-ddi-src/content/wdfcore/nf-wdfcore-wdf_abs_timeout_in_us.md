---
UID: NF:wdfcore.WDF_ABS_TIMEOUT_IN_US
title: WDF_ABS_TIMEOUT_IN_US function (wdfcore.h)
description: The WDF_ABS_TIMEOUT_IN_US function converts a specified number of microseconds to an absolute time value.
old-location: wdf\wdf_abs_timeout_in_us.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_ABS_TIMEOUT_IN_US function"]
ms.keywords: DFTimerObjectRef_0e51f320-984a-4fe2-a077-09aec8b3b011.xml, WDF_ABS_TIMEOUT_IN_US, WDF_ABS_TIMEOUT_IN_US function, kmdf.wdf_abs_timeout_in_us, wdf.wdf_abs_timeout_in_us, wdfcore/WDF_ABS_TIMEOUT_IN_US
req.header: wdfcore.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_ABS_TIMEOUT_IN_US
 - wdfcore/WDF_ABS_TIMEOUT_IN_US
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - None
 - None.dll
api_name:
 - WDF_ABS_TIMEOUT_IN_US
---

# WDF_ABS_TIMEOUT_IN_US function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_ABS_TIMEOUT_IN_US</b> function converts a specified number of microseconds to an absolute time value.

## -parameters

### -param Time 

[in]
The number of microseconds to convert.

## -returns

<b>WDF_ABS_TIMEOUT_IN_US</b> returns the absolute time value, in system time units (100-nanosecond intervals), that represents the number of microseconds that <i>Time</i> specifies.

## -remarks

An absolute time value is a time value that specifies a specific date and time. Absolute times are relative to 00:00, January 1, 1601. If an absolute time value is passed to the system, the system adds the absolute time value to the time value that represents 00:00, January 1, 1601.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcore/nf-wdfcore-wdf_rel_timeout_in_us">WDF_REL_TIMEOUT_IN_US</a>
