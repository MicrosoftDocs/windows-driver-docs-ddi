---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_MS
title: WDF_REL_TIMEOUT_IN_MS function (wdfcore.h)
description: The WDF_REL_TIMEOUT_IN_MS function converts a specified number of milliseconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_ms.htm
tech.root: wdf
ms.assetid: f68b9575-04e4-4046-aec4-b664d8a643d4
ms.date: 02/26/2018
keywords: ["WDF_REL_TIMEOUT_IN_MS function"]
ms.keywords: DFTimerObjectRef_0504a695-4fab-4656-8522-a6c9f0989c2d.xml, WDF_REL_TIMEOUT_IN_MS, WDF_REL_TIMEOUT_IN_MS function, kmdf.wdf_rel_timeout_in_ms, wdf.wdf_rel_timeout_in_ms, wdfcore/WDF_REL_TIMEOUT_IN_MS
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
 - WDF_REL_TIMEOUT_IN_MS
 - wdfcore/WDF_REL_TIMEOUT_IN_MS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - None
 - None.dll
api_name:
 - WDF_REL_TIMEOUT_IN_MS
---

# WDF_REL_TIMEOUT_IN_MS function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REL_TIMEOUT_IN_MS</b> function converts a specified number of milliseconds to a relative time value.

## -parameters

### -param Time 

[in]
The number of milliseconds to convert.

## -returns

<b>WDF_REL_TIMEOUT_IN_MS</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of milliseconds that <i>Time</i> specifies.

## -remarks

A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five milliseconds to a function that accepts a time-out value, the function will time out five milliseconds after it is called.


#### Examples

The following code example starts a timer. The framework will call the timer's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function after ten milliseconds. 

```cpp
BOOLEAN inTimerQueue;

inTimerQueue = WdfTimerStart(
                             timerHandle,
                             WDF_REL_TIMEOUT_IN_MS(10)
                             );
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcore/nf-wdfcore-wdf_abs_timeout_in_ms">WDF_ABS_TIMEOUT_IN_MS</a>

