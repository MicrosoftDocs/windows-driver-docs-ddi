---
UID: NS:pepfx._PEP_PPM_QUERY_PERF_CONSTRAINTS
title: _PEP_PPM_QUERY_PERF_CONSTRAINTS
author: windows-driver-content
description: The PEP_PPM_PERF_CONSTRAINTS structure describes the performance limits to apply to the processor.
old-location: kernel\pep_ppm_perf_constraints.htm
old-project: kernel
ms.assetid: 29B823A2-C645-4DA3-A3BE-4A3ED6A9799F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/PEP_PPM_PERF_CONSTRAINTS, pepfx/PPEP_PPM_PERF_CONSTRAINTS, PEP_PPM_PERF_CONSTRAINTS structure [Kernel-Mode Driver Architecture], PERFORMANCE_LIMIT_DOMAIN_DEPENDENCY, PEP_PPM_PERF_CONSTRAINTS, _PEP_PPM_QUERY_PERF_CONSTRAINTS, kernel.pep_ppm_perf_constraints, PPEP_PPM_PERF_CONSTRAINTS, PERFORMANCE_LIMIT_THERMAL, PERFORMANCE_LIMIT_POWER, PPEP_PPM_PERF_CONSTRAINTS structure pointer [Kernel-Mode Driver Architecture], *PPEP_PPM_PERF_CONSTRAINTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	pepfx.h
apiname: 
-	PEP_PPM_PERF_CONSTRAINTS
product: Windows
targetos: Windows
req.typenames: *PPEP_PPM_PERF_CONSTRAINTS, PEP_PPM_PERF_CONSTRAINTS
---

# _PEP_PPM_QUERY_PERF_CONSTRAINTS structure


## -description


The <b>PEP_PPM_PERF_CONSTRAINTS</b> structure describes the performance limits to apply to the processor.


## -syntax


````
typedef struct _PEP_PPM_QUERY_PERF_CONSTRAINTS {
  ULONG GuaranteedPerformanceLimit;
  ULONG LimitReasons;
} PEP_PPM_PERF_CONSTRAINTS, *PPEP_PPM_PERF_CONSTRAINTS;
````


## -struct-fields




### -field GuaranteedPerformanceLimit

[out] The guaranteed performance threshold in platform-specific units. If nonzero, this value specifies the maximum sustained performance level of the processor, taking into account all known external constraints (power budgeting, thermal constraints, power source, and so on). All processors are expected to be able to simultaneously sustain their guaranteed performance levels. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt629132">Platform Performance Thresholds</a>.


### -field LimitReasons

[out] The reasons for which the processor's performance can be limited. Set this member to zero or to the bitwise-OR of one or more of the following values:
<table>
<tr>
<th>Limit reason</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PERFORMANCE_LIMIT_THERMAL"></a><a id="performance_limit_thermal"></a><dl>
<dt><b>PERFORMANCE_LIMIT_THERMAL</b></dt>
<dt>0x1</dt>
</dl>
</td>
<td width="60%">
The processor performance can be limited due to an out-of-band (that is, non-ACPI Thermal Zone) thermal condition.

</td>
</tr>
<tr>
<td width="40%"><a id="PERFORMANCE_LIMIT_POWER"></a><a id="performance_limit_power"></a><dl>
<dt><b>PERFORMANCE_LIMIT_POWER</b></dt>
<dt>0x2</dt>
</dl>
</td>
<td width="60%">
The processor performance can be limited to keep power consumption of the processor within hardware safety limits.

</td>
</tr>
<tr>
<td width="40%"><a id="PERFORMANCE_LIMIT_DOMAIN_DEPENDENCY"></a><a id="performance_limit_domain_dependency"></a><dl>
<dt><b>PERFORMANCE_LIMIT_DOMAIN_DEPENDENCY</b></dt>
<dt>0x4</dt>
</dl>
</td>
<td width="60%">
The processor performance can be limited because of a voltage or frequency dependency between this processor and another, non-processor device.

</td>
</tr>
</table> 


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186815">PEP_NOTIFY_PPM_PERF_CONSTRAINTS</a> notification. The <b>GuaranteedPerformanceLimit</b> and <b>LimitReasons</b> members contain output values that the platform extension plug-in (PEP) writes to the structure in response to this notification.

The <b>GuaranteedPerformanceLimit</b> member value is specified in platform-specific units. For example, a hardware platform might use a metric such as the processor clock frequency to provide a rough approximation to the amount of processing work that is being done. 



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186815">PEP_NOTIFY_PPM_PERF_CONSTRAINTS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PERF_CONSTRAINTS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

