---
UID: NF:wdfcore.WDF_REL_TIMEOUT_IN_US
title: WDF_REL_TIMEOUT_IN_US function (wdfcore.h)
description: The WDF_REL_TIMEOUT_IN_US function converts a specified number of microseconds to a relative time value.
old-location: wdf\wdf_rel_timeout_in_us.htm
tech.root: wdf
ms.assetid: 202c9741-140e-4d6e-961b-fb92f690e743
ms.date: 02/26/2018
ms.keywords: DFTimerObjectRef_40b7f958-a289-43c2-ba4b-7085cc1659ee.xml, WDF_REL_TIMEOUT_IN_US, WDF_REL_TIMEOUT_IN_US function, kmdf.wdf_rel_timeout_in_us, wdf.wdf_rel_timeout_in_us, wdfcore/WDF_REL_TIMEOUT_IN_US
ms.topic: function
f1_keywords:
 - "wdfcore/WDF_REL_TIMEOUT_IN_US"
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
- WDF_REL_TIMEOUT_IN_US
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REL_TIMEOUT_IN_US function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_REL_TIMEOUT_IN_US</b> function converts a specified number of microseconds to a relative time value.


## -parameters




### -param Time [in]

The number of microseconds to convert.


## -returns



<b>WDF_REL_TIMEOUT_IN_US</b> returns the relative time value, in system time units (100-nanosecond intervals), that represents the number of microseconds that <i>Time</i> specifies.




## -remarks



A relative time is a time value that is relative to the current system time. For example, if a caller passes a relative time value of five microseconds to a function that accepts a time-out value, the function will time out five microseconds after it is called.


#### Examples

The following code example starts a timer. The framework will call the timer's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdftimer/nc-wdftimer-evt_wdf_timer">EvtTimerFunc</a> callback function after one hundred microseconds. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN inTimerQueue;

inTimerQueue = WdfTimerStart(
                             timerHandle,
                             WDF_REL_TIMEOUT_IN_US(100)
                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcore/nf-wdfcore-wdf_abs_timeout_in_us">WDF_ABS_TIMEOUT_IN_US</a>
 

 

