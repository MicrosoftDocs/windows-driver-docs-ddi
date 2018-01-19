---
UID: NF:wdm.KeConvertPerformanceCounterToAuxiliaryCounter
title: KeConvertPerformanceCounterToAuxiliaryCounter function
author: windows-driver-content
description: The KeConvertPerformanceCounterToAuxiliaryCounter routine converts the specified performance counter value into an auxiliary counter value.
old-location: kernel\keconvertperformancecountertoauxiliarycounter.htm
old-project: kernel
ms.assetid: 69F7C73E-C609-4080-8CB8-2F4D9A8C695B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeConvertPerformanceCounterToAuxiliaryCounter
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
req.alt-api: KeConvertPerformanceCounterToAuxiliaryCounter
req.alt-loc: Hal.dll
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeConvertPerformanceCounterToAuxiliaryCounter function



## -description
The  <b>KeConvertPerformanceCounterToAuxiliaryCounter</b> routine converts the specified performance counter value into an auxiliary counter value.



## -syntax

````
NTSTATUS KeConvertPerformanceCounterToAuxiliaryCounter(
  _In_      ULONG64  PerformanceCounterValue,
  _Out_     PULONG64 AuxiliaryCounterValue,
  _Out_opt_ PULONG64 ConversionError
);
````


## -parameters

### -param PerformanceCounterValue [in]

The performance counter value to convert.


### -param AuxiliaryCounterValue [out]

A pointer to the variable that contains the converted auxiliary counter value.


### -param ConversionError [out, optional]

A pointer to a variable that contains the estimated conversion error in units of nanosecond.


## -returns
<b>KeConvertPerformanceCounterToAuxiliaryCounter</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The conversion succeeded.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>Auxiliary counter is not supported.
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>The <i>PerformanceCounterValue</i> value is not valid. For example, the value is earlier than the last system boot/recovery, or is out of the +/- 10s range compared to the current performance counter value.
<dl>
<dt><b>STATUS_UNSUCCESSFUL </b></dt>
</dl>The routine cannot convert the specified value with acceptable accuracy.

 


## -remarks
Make sure that the specified performance counter value is:

The <i>ConversionError</i> value is the difference, in nanoseconds, between the expected calculated value and the actual calculated value for the auxiliary counter.
If the <i>ConversionError</i> value is greater than the expected value (determined by you), then call the routine again. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keconvertauxiliarycountertoperformancecounter.md">KeConvertAuxiliaryCounterToPerformanceCounter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeConvertPerformanceCounterToAuxiliaryCounter routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

