---
UID: NF:wdm.KeConvertAuxiliaryCounterToPerformanceCounter
title: KeConvertAuxiliaryCounterToPerformanceCounter function (wdm.h)
description: The KeConvertAuxiliaryCounterToPerformanceCounter routine converts the specified auxiliary counter value into a performance counter value.
old-location: kernel\keconvertauxiliarycountertoperformancecounter.htm
tech.root: kernel
ms.assetid: 90F4CE6D-F51A-4B18-B328-63AF4D71A690
ms.date: 04/30/2018
keywords: ["KeConvertAuxiliaryCounterToPerformanceCounter function"]
ms.keywords: KeConvertAuxiliaryCounterToPerformanceCounter, KeConvertAuxiliaryCounterToPerformanceCounter routine [Kernel-Mode Driver Architecture], kernel.keconvertauxiliarycountertoperformancecounter, wdm/KeConvertAuxiliaryCounterToPerformanceCounter
f1_keywords:
 - "wdm/KeConvertAuxiliaryCounterToPerformanceCounter"
 - "KeConvertAuxiliaryCounterToPerformanceCounter"
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
- KeConvertAuxiliaryCounterToPerformanceCounter
targetos: Windows
req.typenames: 
---

# KeConvertAuxiliaryCounterToPerformanceCounter function


## -description


The  <b>KeConvertAuxiliaryCounterToPerformanceCounter</b> routine converts the specified auxiliary counter value into a performance  counter value.





## -parameters




### -param AuxiliaryCounterValue [in]

The auxiliary counter value to convert.


### -param PerformanceCounterValue [out]

A pointer to the variable that contains the converted performance counter value.


### -param ConversionError [out, optional]

A pointer to a variable that contains the estimated conversion error in units of nanosecond.


## -returns



<b>KeConvertAuxiliaryCounterToPerformanceCounter</b> can return one of the following:

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
The <i>AuxiliaryCounterValue</i> value is not valid. For example, the value is earlier than the last system boot/recovery, or is out of the +/- 10s range compared to the current auxiliary counter value.

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



Make sure that the specified auxiliary counter value is within +/- 10s compared to the current value.

 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keconvertperformancecountertoauxiliarycounter">KeConvertPerformanceCounterToAuxiliaryCounter</a>
 

 

