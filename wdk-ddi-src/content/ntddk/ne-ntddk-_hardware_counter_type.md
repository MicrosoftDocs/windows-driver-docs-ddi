---
UID: NE:ntddk._HARDWARE_COUNTER_TYPE
title: _HARDWARE_COUNTER_TYPE (ntddk.h)
description: The HARDWARE_COUNTER_TYPE enumeration specifies the type of a hardware counter.
old-location: kernel\hardware_counter_type.htm
tech.root: kernel
ms.assetid: 837f5a55-ca07-4462-85d7-203d02df168c
ms.date: 04/30/2018
keywords: ["_HARDWARE_COUNTER_TYPE enumeration"]
ms.keywords: "*PHARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE, HARDWARE_COUNTER_TYPE enumeration [Kernel-Mode Driver Architecture], MaxHardwareCounterType, PHARDWARE_COUNTER_TYPE, PHARDWARE_COUNTER_TYPE enumeration pointer [Kernel-Mode Driver Architecture], PMCCounter, _HARDWARE_COUNTER_TYPE, kernel.hardware_counter_type, ntddk/HARDWARE_COUNTER_TYPE, ntddk/MaxHardwareCounterType, ntddk/PHARDWARE_COUNTER_TYPE, ntddk/PMCCounter, sysenum_861db9b8-cd2d-4cfe-ae99-5c292f28c420.xml"
f1_keywords:
 - "ntddk/HARDWARE_COUNTER_TYPE"
 - "HARDWARE_COUNTER_TYPE"
req.header: ntddk.h
req.include-header: Winnt.h, Ntddk.h
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
- ntddk.h
api_name:
- HARDWARE_COUNTER_TYPE
product:
- Windows
targetos: Windows
req.typenames: HARDWARE_COUNTER_TYPE, *PHARDWARE_COUNTER_TYPE
---

# _HARDWARE_COUNTER_TYPE enumeration


## -description


The <b>HARDWARE_COUNTER_TYPE</b> enumeration specifies the type of a hardware counter.


## -enum-fields




### -field PMCCounter

Performance monitor counter. This type of counter is used by thread-profiling applications. 


### -field MaxHardwareCounterType

The maximum value in this enumeration type.


## -remarks



The <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_hardware_counter">HARDWARE_COUNTER</a> structure contains a <b>HARDWARE_COUNTER_TYPE</b> enumeration value. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_hardware_counter">HARDWARE_COUNTER</a>
 

 

