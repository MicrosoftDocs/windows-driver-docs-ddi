---
UID: NS:wdm._POWER_STATE
title: "_POWER_STATE"
author: windows-driver-content
description: The POWER_STATE union specifies a system power state value or a device power state value.
old-location: kernel\power_state.htm
old-project: kernel
ms.assetid: c3730035-74fc-421a-89dc-7411e53950f5
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPOWER_STATE, POWER_STATE, POWER_STATE union [Kernel-Mode Driver Architecture], PPOWER_STATE, PPOWER_STATE union pointer [Kernel-Mode Driver Architecture], _POWER_STATE, kernel.power_state, kstruct_c_a0fca0b4-3d45-48e4-b3ee-ba473ac08347.xml, wdm/POWER_STATE, wdm/PPOWER_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	POWER_STATE
product:
- Windows
targetos: Windows
req.typenames: POWER_STATE, *PPOWER_STATE
req.product: Windows 10 or later.
---

# _POWER_STATE structure


## -description


The <b>POWER_STATE</b> union specifies a <a href="https://msdn.microsoft.com/bb30bc89-d1f2-4cb3-bcfb-fb76c69dba27">system power state</a> value or a device power state value.


## -struct-fields




### -field SystemState

A system power state value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>. 


### -field DeviceState

A device power state value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>. 


## -remarks



The <b>POWER_STATE</b> union is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559851">POWER_STATE_TYPE</a> enumeration type to specify a system power state value or a device power state value. This union is also used in cases where the power state type is implicitly determined by the context in which it is used. For example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559734">PoRequestPowerIrp</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559765">PoSetPowerState</a>.

For more information about power management, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548108">Introduction to Power Management</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559851">POWER_STATE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559734">PoRequestPowerIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559765">PoSetPowerState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>
 

 

