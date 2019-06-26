---
UID: NF:wdfcore.WDF_ABS_TIMEOUT_IN_SEC
title: WDF_ABS_TIMEOUT_IN_SEC function (wdfcore.h)
description: The WDF_ABS_TIMEOUT_IN_SEC function converts a specified number of seconds to an absolute time value.
old-location: wdf\wdf_abs_timeout_in_sec.htm
tech.root: wdf
ms.assetid: 492bdc23-7e55-4e6d-9d7c-189a94934049
ms.date: 02/26/2018
ms.keywords: DFTimerObjectRef_681839d3-3160-4f57-beeb-b5fe66dad3fe.xml, WDF_ABS_TIMEOUT_IN_SEC, WDF_ABS_TIMEOUT_IN_SEC function, kmdf.wdf_abs_timeout_in_sec, wdf.wdf_abs_timeout_in_sec, wdfcore/WDF_ABS_TIMEOUT_IN_SEC
ms.topic: function
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
- WDF_ABS_TIMEOUT_IN_SEC
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_ABS_TIMEOUT_IN_SEC function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_ABS_TIMEOUT_IN_SEC</b> function converts a specified number of seconds to an absolute time value.


## -parameters




### -param Time [in]

The number of seconds to convert.


## -returns



<b>WDF_ABS_TIMEOUT_IN_SEC</b> returns the absolute time value, in system time units (100-nanosecond intervals), that represents the number of seconds that <i>Time</i> specifies.




## -remarks



An absolute time value is a time value that specifies a specific date and time. Absolute times are relative to 00:00, January 1, 1601. If an absolute time value is passed to the system, the system adds the absolute time value to the time value that represents 00:00, January 1, 1601.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcore/nf-wdfcore-wdf_rel_timeout_in_sec">WDF_REL_TIMEOUT_IN_SEC</a>
 

 

