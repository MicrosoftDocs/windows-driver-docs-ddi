---
UID: NF:wdm.KeConvertAuxiliaryCounterToPerformanceCounter
title: KeConvertAuxiliaryCounterToPerformanceCounter function
author: windows-driver-content
description: The KeConvertAuxiliaryCounterToPerformanceCounter routine converts the specified auxiliary counter value into a performance counter value.
old-location: kernel\keconvertauxiliarycountertoperformancecounter.htm
old-project: kernel
ms.assetid: 90F4CE6D-F51A-4B18-B328-63AF4D71A690
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeConvertAuxiliaryCounterToPerformanceCounter, KeConvertAuxiliaryCounterToPerformanceCounter routine [Kernel-Mode Driver Architecture], kernel.keconvertauxiliarycountertoperformancecounter, wdm/KeConvertAuxiliaryCounterToPerformanceCounter
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hal.dll
api_name:
-	KeConvertAuxiliaryCounterToPerformanceCounter
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
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




<a href="https://msdn.microsoft.com/library/windows/hardware/mt146561">KeConvertPerformanceCounterToAuxiliaryCounter</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeConvertAuxiliaryCounterToPerformanceCounter routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

