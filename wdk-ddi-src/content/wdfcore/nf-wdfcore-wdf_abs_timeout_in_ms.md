---
UID: NF:wdfcore.WDF_ABS_TIMEOUT_IN_MS
title: WDF_ABS_TIMEOUT_IN_MS function (wdfcore.h)
description: The WDF_ABS_TIMEOUT_IN_MS function converts a specified number of milliseconds to an absolute time value.
old-location: wdf\wdf_abs_timeout_in_ms.htm
tech.root: wdf
ms.assetid: 271d2b39-53a3-454b-97d0-0bace8504b48
ms.date: 02/26/2018
ms.keywords: DFTimerObjectRef_6ebc68ca-16c5-4948-ac68-d9247b8074f3.xml, WDF_ABS_TIMEOUT_IN_MS, WDF_ABS_TIMEOUT_IN_MS function, kmdf.wdf_abs_timeout_in_ms, wdf.wdf_abs_timeout_in_ms, wdfcore/WDF_ABS_TIMEOUT_IN_MS
ms.topic: function
f1_keywords:
 - "wdfcore/WDF_ABS_TIMEOUT_IN_MS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- None
- None.dll
api_name:
- WDF_ABS_TIMEOUT_IN_MS
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_ABS_TIMEOUT_IN_MS function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_ABS_TIMEOUT_IN_MS</b> function converts a specified number of milliseconds to an absolute time value.


## -parameters




### -param Time [in]

The number of milliseconds to convert.


## -returns



<b>WDF_ABS_TIMEOUT_IN_MS</b> returns the absolute time value, in system time units (100-nanosecond intervals), that represents the number of milliseconds that <i>Time</i> specifies.




## -remarks



An absolute time value is a time value that specifies a specific date and time. Absolute times are relative to 00:00, January 1, 1601. If an absolute time value is passed to the system, the system adds the absolute time value to the time value that represents 00:00, January 1, 1601.

```cpp

```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcore/nf-wdfcore-wdf_rel_timeout_in_ms">WDF_REL_TIMEOUT_IN_MS</a>
 

 

