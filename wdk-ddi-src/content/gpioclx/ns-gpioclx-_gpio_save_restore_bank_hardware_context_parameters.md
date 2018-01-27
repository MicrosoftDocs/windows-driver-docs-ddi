---
UID: NS:gpioclx._GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
title: _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
author: windows-driver-content
description: The GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure describes a bank of general-purpose I/O (GPIO) pins whose hardware state is to be saved or restored.
old-location: gpio\gpio_save_restore_bank_hardware_context_parameters.htm
old-project: GPIO
ms.assetid: 7A93C53C-8E60-4C57-BDEC-6868AB5E400D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gpioclx/PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, GPIO.gpio_save_restore_bank_hardware_context_parameters, GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure [Parallel Ports], *PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, gpioclx/GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure pointer [Parallel Ports]
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Gpioclx.h
apiname: 
-	GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: *PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS
---

# _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure


## -description


The <b>GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</b> structure describes a bank of general-purpose I/O (GPIO) pins whose hardware state is to be saved or restored.


## -syntax


````
typedef struct _GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS {
  BANK_ID                                       BankId;
  ULONG                                         State;
  GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_FLAGS Flags;
} GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS, *PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS;
````


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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

