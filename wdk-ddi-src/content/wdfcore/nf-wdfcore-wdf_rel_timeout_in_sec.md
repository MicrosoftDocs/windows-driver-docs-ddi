---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_SEC
title: WDF_REL_TIMEOUT_IN_SEC function (wdfcore.h)
description: The WDF_REL_TIMEOUT_IN_SEC function converts a specified number of seconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_sec.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_REL_TIMEOUT_IN_SEC function"]
ms.keywords: DFTimerObjectRef_2c5d8c96-3c4d-484d-9d60-656c4c4a7cc5.xml, WDF_REL_TIMEOUT_IN_SEC, WDF_REL_TIMEOUT_IN_SEC function, kmdf.wdf_rel_timeout_in_sec, wdf.wdf_rel_timeout_in_sec, wdfcore/WDF_REL_TIMEOUT_IN_SEC
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
 - WDF_REL_TIMEOUT_IN_SEC
 - wdfcore/WDF_REL_TIMEOUT_IN_SEC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - None
 - None.dll
api_name:
 - WDF_REL_TIMEOUT_IN_SEC
---

# WDF_REL_TIMEOUT_IN_SEC function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REL_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to a relative time value.

## -parameters

### -param Time [in]


The number of seconds to convert.

## -returns

<b>WDF_REL_TIMEOUT_IN_SEC</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.

## -remarks

A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five seconds to a function that accepts a time-out value, the function will time out five seconds after it is called.


#### Examples

The following code example specifies a relative timeout value of 5 seconds for an I/O request.

```cpp
WDF_REQUEST_SEND_OPTIONS  requestSendOptions;
...
requestSendOptions.Timeout = WDF_REL_TIMEOUT_IN_SEC(5);
...
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcore/nf-wdfcore-wdf_abs_timeout_in_sec">WDF_ABS_TIMEOUT_IN_SEC</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/ns-wdfrequest-_wdf_request_send_options">WDF_REQUEST_SEND_OPTIONS</a>
