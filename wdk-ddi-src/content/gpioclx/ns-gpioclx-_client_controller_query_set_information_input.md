---
UID: NS:gpioclx._CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
title: _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT (gpioclx.h)
description: The CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure contains a request for the hardware attributes of the general-purpose I/O (GPIO) controller.
old-location: gpio\client_controller_query_set_information_input.htm
tech.root: GPIO
ms.date: 07/22/2022
keywords: ["CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure"]
ms.keywords: "*PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure [Parallel Ports], GPIO.client_controller_query_set_information_input, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure pointer [Parallel Ports], _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT"
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
req.typenames: CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, *PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
f1_keywords:
 - _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - gpioclx/_CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
 - CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
---

# _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure

## -description

The **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT** structure contains a request for the hardware attributes of the general-purpose I/O (GPIO) controller.

## -struct-fields

### -field RequestType

The type of attribute information that is being requested. This member is set to a [CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE](./ne-gpioclx-_client_controller_query_set_request_type.md) enumeration value.

### -field Size

Specifies the size, in bytes, of the **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT** structure.

### -field Flags

A set of flag bits that supply additional information about the type of attribute request indicated by the **RequestType** member. No flags are currently defined for the **Flags** member.

### -field BankPowerInformation

A structure that contains information about the GPIO bank whose power attributes are being requested.

### -field BankPowerInformation.BankId

The identifier for a bank of GPIO pins. If M is the number of banks in the GPIO controller, **BankId** is an integer in the range 0 to M–1\. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the [CLIENT_QueryControllerBasicInformation](./nc-gpioclx-gpio_client_query_controller_basic_information.md) event callback function. For more information, see Remarks in [CLIENT_CONTROLLER_BASIC_INFORMATION](./ns-gpioclx-_client_controller_basic_information.md).

### -field BankInterruptBinding

A structure that contains information about the interrupt resources that are assigned to the GPIO controller.

### -field BankInterruptBinding.ResourcesTranslated

A handle to a framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.

### -field BankInterruptBinding.ResourcesRaw

A handle to a framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.

### -field BankInterruptBinding.TotalBanks

The number of banks in the GPIO controller. This member indicates the expected length of the **BankInterruptBinding.ResourceMapping** array in the caller-allocated [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT](./ns-gpioclx-_client_controller_query_set_information_output.md) structure, if the caller supplies a non-NULL pointer to this structure.

### -field ControllerFunctionBankMapping

A structure that contains information about an I/O control request (IOCTL).

### -field ControllerFunctionBankMapping.InputBuffer

A pointer to the input buffer for the IOCTL.

### -field ControllerFunctionBankMapping.InputBufferSize

The size, in bytes, of the input buffer for the IOCTL.

### -field ControllerFunctionBankMapping.OutputBufferSize

The size, in bytes, of the output buffer for the IOCTL.

### -field ControllerFunctionBankMapping.TotalBanks

The number of banks in the GPIO controller. This member indicates the expected length of the **ControllerFunctionBankMapping.Mapping** array in the caller-allocated [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT](./ns-gpioclx-_client_controller_query_set_information_output.md) structure, if the caller supplies a non-NULL pointer to this structure.

## -remarks

The unnamed union contains input information for the various types of attribute requests. The **RequestType** member determines which member of this union is used. The following table shows the union member that corresponds to each valid **RequestType** value.

| RequestType value | Union member |
|--|--|
| QueryBankPowerInformation | BankPowerInformation |
| QueryBankInterruptBindingInformation | BankInterruptBinding |
| QueryControllerFunctionBankMappingInformation | ControllerFunctionBankMapping |

The *InputBuffer* parameter of the [CLIENT_QuerySetControllerInformation](./nc-gpioclx-gpio_client_query_set_controller_information.md) function is a pointer to a **CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT** structure.

## -see-also

- [CLIENT_CONTROLLER_BASIC_INFORMATION](./ns-gpioclx-_client_controller_basic_information.md)
- [CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT](./ns-gpioclx-_client_controller_query_set_information_output.md)
- [CLIENT_QueryControllerBasicInformation](./nc-gpioclx-gpio_client_query_controller_basic_information.md)
- [CLIENT_QuerySetControllerInformation](./nc-gpioclx-gpio_client_query_set_controller_information.md)