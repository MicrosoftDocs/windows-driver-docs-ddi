---
UID: NS:ntddk._HARDWARE_COUNTER
title: _HARDWARE_COUNTER (ntddk.h)
description: The HARDWARE_COUNTER structure contains information about a hardware counter.
old-location: kernel\hardware_counter.htm
tech.root: kernel
ms.assetid: 15eeeb07-b71f-4868-8854-6a5034d3f8c6
ms.date: 04/30/2018
ms.keywords: "*PHARDWARE_COUNTER, HARDWARE_COUNTER, HARDWARE_COUNTER structure [Kernel-Mode Driver Architecture], PHARDWARE_COUNTER, PHARDWARE_COUNTER structure pointer [Kernel-Mode Driver Architecture], _HARDWARE_COUNTER, kernel.hardware_counter, kstruct_b_3e230097-13da-4e6b-bb89-baf3563c3570.xml, ntddk/HARDWARE_COUNTER, ntddk/PHARDWARE_COUNTER"
ms.topic: struct
f1_keywords:
 - "ntddk/HARDWARE_COUNTER"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddk.h
api_name:
- HARDWARE_COUNTER
product:
- Windows
targetos: Windows
req.typenames: HARDWARE_COUNTER, *PHARDWARE_COUNTER
---

# _HARDWARE_COUNTER structure


## -description


The <b>HARDWARE_COUNTER</b> structure contains information about a hardware counter. 


## -struct-fields




### -field Type

Specifies the type of the hardware counter. Set this member to the following <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_hardware_counter_type">HARDWARE_COUNTER_TYPE</a> enumeration value:

<ul>
<li>
<b>PMCCounter</b>

</li>
</ul>

### -field Reserved

Reserved for use by the operating system. Initialize this member to zero. 


### -field Index

Specifies the hardware counter index. Each hardware counter in a performance monitoring unit (PMU) for a processor is identified by an index.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhardwarecounterconfiguration">KeQueryHardwareCounterConfiguration</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesethardwarecounterconfiguration">KeSetHardwareCounterConfiguration</a> routines. 

The <b>Type</b> member specifies the type of hardware counter that is described by the structure. In Windows 7, the only defined hardware counter type is <b>PMCCounter</b>, which is a performance monitor counter. This type of counter is used by thread-profiling applications. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_hardware_counter_type">HARDWARE_COUNTER_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhardwarecounterconfiguration">KeQueryHardwareCounterConfiguration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kesethardwarecounterconfiguration">KeSetHardwareCounterConfiguration</a>
 

 

