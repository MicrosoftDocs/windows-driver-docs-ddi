---
UID: NS:gpioclx._CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
title: _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT (gpioclx.h)
description: The CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure contains a set of general-purpose I/O (GPIO) controller attributes that were requested by the GPIO framework extension (GpioClx).
old-location: gpio\client_controller_query_set_information_output.htm
tech.root: GPIO
ms.date: 07/22/2022
keywords: ["CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure"]
ms.keywords: "*PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure [Parallel Ports], GPIO.client_controller_query_set_information_output, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure pointer [Parallel Ports], _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT"
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
targetos: Windows
req.typenames: CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, *PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
f1_keywords:
 - _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - gpioclx/_CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
 - CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
---

# _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure

## -description

The **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT** structure contains a set of general-purpose I/O (GPIO) controller attributes that were requested by the GPIO framework extension (GpioClx).

## -struct-fields

### -field Version

Specifies the version number of this structure.

### -field Size

Specifies the size, in bytes, of this structure.

### -field BankPowerInformation

A [CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT](./ns-gpioclx-_client_query_bank_power_information_output.md) structure that contains the power attributes of the GPIO bank that is identified by the **BankPowerInformation.BankId** member of the corresponding **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT** structure.

### -field BankInterruptBinding

A structure that contains information about the binding of interrupt resources to GPIO banks.

### -field BankInterruptBinding.ResourceMapping

An array of interrupt resource numbers. The number of elements in the array equals the number of GPIO banks. If N is the number of banks in the GPIO controller, the banks are numbered 0 to N–1. Element 0 of the array contains the interrupt resource number that is bound to bank 0, element 1 contains the interrupt resource number that is bound to bank 1, and so on. No more than one interrupt resource can be bound to a GPIO bank, but two or more banks might share an interrupt resource. If a bank is not bound to an interrupt resource, the corresponding array element is set to **GPIO_BANK_INTERRUPT_BINDING_RESERVED_INDEX** (0xffff).

An interrupt resource is identified by its resource number, which is the index of the resource in the **ResourcesTranslated** or **ResourcesRaw** resource list in the **BankInterruptBinding** member of the [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT](./ns-gpioclx-_client_controller_query_set_information_input.md) structure. If a list contains M resources, the resources are numbered 0 to M-1\. Only resource numbers that correspond to interrupt resources in the resource list can appear in the **ResourceMapping** array.

### -field ControllerFunctionBankMapping

A structure that contains information about the GPIO banks that must be in the F0 (fully on) power state to handle an I/O control request (IOCTL).

### -field ControllerFunctionBankMapping.Mapping

An array of BOOLEAN values that indicates the mapping of required F0 power states to GPIO banks. The number of elements in the array equals the number of GPIO banks. If N is the number of banks in the GPIO controller, the banks are numbered 0 to N–1. Element 0 of the array contains the mapping for bank 0, element 1 contains the mapping for bank 1, and so on. If an element is **TRUE**, the corresponding GPIO bank must be in the F0 power state to handle the IOCTL. If an element is **FALSE**, the corresponding bank is not required to be in the F0 power state.

## -remarks

The unnamed union contains output information for the various types of attribute requests. The **RequestType** member of the corresponding [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT](./ns-gpioclx-_client_controller_query_set_information_input.md) structure determines which of these members is used.

The optional *OutputBuffer* parameter of the [CLIENT_QuerySetControllerInformation](./nc-gpioclx-gpio_client_query_set_controller_information.md) function is a pointer to a caller-allocated **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT** structure. The function writes the requested attribute information to this structure, if *OutputBuffer* is non-NULL.

## -see-also

- [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT](./ns-gpioclx-_client_controller_query_set_information_input.md)
- [CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT](./ns-gpioclx-_client_query_bank_power_information_output.md)
- [CLIENT_QuerySetControllerInformation](./nc-gpioclx-gpio_client_query_set_controller_information.md)