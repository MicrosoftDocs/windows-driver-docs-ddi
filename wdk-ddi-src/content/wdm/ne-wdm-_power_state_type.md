---
UID: NE:wdm._POWER_STATE_TYPE
title: "_POWER_STATE_TYPE"
author: windows-driver-content
description: The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state.
old-location: kernel\power_state_type.htm
old-project: kernel
ms.assetid: d0e97474-4119-4359-a9f9-644c82df7fab
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPOWER_STATE_TYPE, DevicePowerState, POWER_STATE_TYPE, POWER_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PPOWER_STATE_TYPE, PPOWER_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], SystemPowerState, _POWER_STATE_TYPE, kernel.power_state_type, sysenum_bdfdaea1-ec64-4b74-96d0-95641797ebb4.xml, wdm/DevicePowerState, wdm/POWER_STATE_TYPE, wdm/PPOWER_STATE_TYPE, wdm/SystemPowerState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	POWER_STATE_TYPE
product:
- Windows
targetos: Windows
req.typenames: POWER_STATE_TYPE, *PPOWER_STATE_TYPE
---

# _POWER_STATE_TYPE enumeration


## -description


The <b>POWER_STATE_TYPE</b> enumeration type indicates that a power state value is a system power state or a device power state.


## -enum-fields




### -field SystemPowerState

Indicates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a> value.


### -field DevicePowerState

Indicates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a> value.


## -remarks



The <b>POWER_STATE_TYPE</b> enumeration type is used in conjunction with a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559842">POWER_STATE</a> to indicate that the power state value is a system power state value or a device power state value. For an example, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559765">PoSetPowerState</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554628">DEVICE_POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559842">POWER_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559765">PoSetPowerState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564565">SYSTEM_POWER_STATE</a>
 

 

