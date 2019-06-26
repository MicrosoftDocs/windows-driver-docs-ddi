---
UID: NF:wdm.KeConvertPerformanceCounterToAuxiliaryCounter
title: KeConvertPerformanceCounterToAuxiliaryCounter function (wdm.h)
description: The KeConvertPerformanceCounterToAuxiliaryCounter routine converts the specified performance counter value into an auxiliary counter value.
old-location: kernel\keconvertperformancecountertoauxiliarycounter.htm
tech.root: kernel
ms.assetid: 69F7C73E-C609-4080-8CB8-2F4D9A8C695B
ms.date: 04/30/2018
ms.keywords: KeConvertPerformanceCounterToAuxiliaryCounter, KeConvertPerformanceCounterToAuxiliaryCounter routine [Kernel-Mode Driver Architecture], kernel.keconvertperformancecountertoauxiliarycounter, wdm/KeConvertPerformanceCounterToAuxiliaryCounter
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Hal.dll
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Hal.dll
api_name:
- KeConvertPerformanceCounterToAuxiliaryCounter
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeConvertPerformanceCounterToAuxiliaryCounter function


## -description


The  <b>KeConvertPerformanceCounterToAuxiliaryCounter</b> routine converts the specified performance counter value into an auxiliary counter value.


## -parameters




### -param PerformanceCounterValue [in]

The performance counter value to convert.


### -param AuxiliaryCounterValue [out]

A pointer to the variable that contains the converted auxiliary counter value.


### -param ConversionError [out, optional]

A pointer to a variable that contains the estimated conversion error in units of nanosecond.


## -returns



<b>KeConvertPerformanceCounterToAuxiliaryCounter</b> can return one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The conversion succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Auxiliary counter is not supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The <i>PerformanceCounterValue</i> value is not valid. For example, the value is earlier than the last system boot/recovery, or is out of the +/- 10s range compared to the current performance counter value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL </b></dt>
</dl>
</td>
<td width="60%">
The routine cannot convert the specified value with acceptable accuracy.

</td>
</tr>
</table>
 




## -remarks



Make sure that the specified performance counter value is:

<ul>
<li>Within +/- 10s compared to the current performance counter read value.

</li>
<li>Not earlier than the recorded performance counter value at the last system boot or recovery from S3/S4 state.</li>
</ul>
The <i>ConversionError</i> value is the difference, in nanoseconds, between the expected calculated value and the actual calculated value for the auxiliary counter.
If the <i>ConversionError</i> value is greater than the expected value (determined by you), then call the routine again. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keconvertauxiliarycountertoperformancecounter">KeConvertAuxiliaryCounterToPerformanceCounter</a>
 

 

