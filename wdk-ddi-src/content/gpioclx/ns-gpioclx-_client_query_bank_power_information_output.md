---
UID: NS:gpioclx._CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
title: "_CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT"
author: windows-driver-content
description: The CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_query_bank_power_information_output.htm
old-project: GPIO
ms.assetid: 156115CB-FF0C-4E53-BB7E-CF98420DF443
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure [Parallel Ports], GPIO.client_query_bank_power_information_output, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure pointer [Parallel Ports], _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, gpioclx/CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, gpioclx/PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT, *PCLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT
---

# _CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT structure


## -description


The <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b> structure contains information about the power-management capabilities of a bank of general-purpose I/O (GPIO) pins.


## -struct-fields




### -field F1IdleStateParameters

A <b>PO_FX_COMPONENT_IDLE_STATE</b> structure that describes the parameters (transition latency, residency requirement, and so on) for the F1 power state of the GPIO bank. For more information about these parameters, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439581">PO_FX_COMPONENT_IDLE_STATE</a>.


#### - ( unnamed struct )

A set of power-management flag bits.



#### F1StateSupported

Indicates whether the GPIO bank supports <a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">component-level power management</a>. If this flag is set, the GPIO bank supports component-level power management. Otherwise, it does not. A GPIO bank that supports power management can change between the F0 (fully powered) state and the F1 (low-power) state independently of the Fx power states of the other banks in the GPIO controller. A GPIO bank that does not support component-level power management is always in the F0 power state when the controller is in the D0 power state.



#### Reserved

Not used.


## -remarks



The <b>BankPowerInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure is a structure of type <b>CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</b>.

For more information about GPIO banks, see <a href="https://msdn.microsoft.com/D9425459-E052-48D8-A4F3-91387AE7059A">Partioning a GPIO Controller into Banks of Pins</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439581">PO_FX_COMPONENT_IDLE_STATE</a>
 

 

