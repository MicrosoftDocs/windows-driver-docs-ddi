---
UID: NS:gpioclx._GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
title: _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS (gpioclx.h)
description: The GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure describes a bank of general-purpose I/O (GPIO) pins whose hardware state is to be saved or restored.
old-location: gpio\gpio_save_restore_bank_hardware_context_parameters.htm
tech.root: GPIO
ms.assetid: 7A93C53C-8E60-4C57-BDEC-6868AB5E400D
ms.date: 02/15/2018
ms.keywords: "*PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, GPIO.gpio_save_restore_bank_hardware_context_parameters, GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure [Parallel Ports], PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure pointer [Parallel Ports], _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, gpioclx/GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, gpioclx/PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Gpioclx.h
api_name:
- GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, *PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
---

# _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure


## -description


The <b>GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</b> structure describes a bank of general-purpose I/O (GPIO) pins whose hardware state is to be saved or restored.


## -struct-fields




### -field BankId

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field State

The target component power state. A save operation occurs before the specified bank of GPIO pins makes the transition from the F0 (fully on) state to the target component power state, Fx. A restore operation occurs after the bank makes the transition from Fx to F0.


### -field Flags

A set of flags to control bank hardware save and restore operations. If the <b>CriticalTransition</b> flag bit is set, this idle state transition is being done as part of a critical transition in which the power engine plug-in (PEP) puts the system into a low-power state.


## -remarks



The <i>Parameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a> event callback functions is a pointer to a caller-allocated <b>GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a>
 

 

