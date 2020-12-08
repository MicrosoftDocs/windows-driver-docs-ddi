---
UID: NS:gpioclx._GPIO_CLIENT_REGISTRATION_PACKET
title: _GPIO_CLIENT_REGISTRATION_PACKET (gpioclx.h)
description: The GPIO_CLIENT_REGISTRATION_PACKET structure contains registration information that the general-purpose I/O (GPIO) controller driver passes to the GPIO framework extension (GpioClx).
old-location: gpio\gpio_client_registration_packet.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_REGISTRATION_PACKET structure"]
ms.keywords: "*PGPIO_CLIENT_REGISTRATION_PACKET, GPIO.gpio_client_registration_packet, GPIO_CLIENT_REGISTRATION_PACKET, GPIO_CLIENT_REGISTRATION_PACKET structure [Parallel Ports], PGPIO_CLIENT_REGISTRATION_PACKET, PGPIO_CLIENT_REGISTRATION_PACKET structure pointer [Parallel Ports], _GPIO_CLIENT_REGISTRATION_PACKET, gpioclx/GPIO_CLIENT_REGISTRATION_PACKET, gpioclx/PGPIO_CLIENT_REGISTRATION_PACKET"
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
req.typenames: GPIO_CLIENT_REGISTRATION_PACKET, *PGPIO_CLIENT_REGISTRATION_PACKET
f1_keywords:
 - _GPIO_CLIENT_REGISTRATION_PACKET
 - gpioclx/_GPIO_CLIENT_REGISTRATION_PACKET
 - PGPIO_CLIENT_REGISTRATION_PACKET
 - gpioclx/PGPIO_CLIENT_REGISTRATION_PACKET
 - GPIO_CLIENT_REGISTRATION_PACKET
 - gpioclx/GPIO_CLIENT_REGISTRATION_PACKET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - GPIO_CLIENT_REGISTRATION_PACKET
---

# _GPIO_CLIENT_REGISTRATION_PACKET structure


## -description

The <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure contains registration information that the general-purpose I/O (GPIO) controller driver passes to the GPIO framework extension (GpioClx).

## -struct-fields

### -field Version

The version number for the GPIO interface that the GPIO controller driver supports. Set this member to the value GPIO_CLIENT_VERSION, which is defined in the Gpioclx.h header file.

### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>GPIO_CLIENT_REGISTRATION_PACKET</b>).

### -field Flags

A set of flags that indicate which registration options are selected. No flags are currently defined for registration options. Set this member to zero.

### -field ControllerContextSize

The required device context size, in bytes. The <a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method allocates a device context of this size. When GpioClx calls any registered callback function in the <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure, GpioClx passes this device context to the callback function as a parameter. The callback functions use this context to access and update the driver's information about the state of the GPIO controller device. For more information, see <a href="/windows-hardware/drivers/gpio/gpio-device-contexts">GPIO Device Contexts</a>.

### -field Reserved

Reserved for future use. Set this member to zero.

### -field CLIENT_PrepareController

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_prepare_controller">CLIENT_PrepareController</a> event callback function.

### -field CLIENT_ReleaseController

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_release_controller">CLIENT_ReleaseController</a> event callback function.

### -field CLIENT_StartController

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_start_controller">CLIENT_StartController</a> event callback function.

### -field CLIENT_StopController

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_stop_controller">CLIENT_StopController</a> event callback function.

### -field CLIENT_QueryControllerBasicInformation

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function.

### -field CLIENT_QuerySetControllerInformation

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_set_controller_information">CLIENT_QuerySetControllerInformation</a> event callback function.

### -field CLIENT_EnableInterrupt

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a> event callback function.

### -field CLIENT_DisableInterrupt

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disable_interrupt">CLIENT_DisableInterrupt</a> event callback function.

### -field CLIENT_UnmaskInterrupt

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_unmask_interrupt">CLIENT_UnmaskInterrupt</a> event callback function.

### -field CLIENT_MaskInterrupts

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_mask_interrupts">CLIENT_MaskInterrupts</a> event callback function.

### -field CLIENT_QueryActiveInterrupts

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_active_interrupts">CLIENT_QueryActiveInterrupts</a> event callback function.

### -field CLIENT_ClearActiveInterrupts

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_clear_active_interrupts">CLIENT_ClearActiveInterrupts</a> event callback function.

### -field CLIENT_ConnectIoPins

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_connect_io_pins">CLIENT_ConnectIoPins</a> event callback function.

### -field CLIENT_DisconnectIoPins

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disconnect_io_pins">CLIENT_DisconnectIoPins</a> event callback function.

### -field CLIENT_ReadGpioPins

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins">CLIENT_ReadGpioPins</a> event callback function.

### -field CLIENT_ReadGpioPinsUsingMask

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins_mask">CLIENT_ReadGpioPinsUsingMask</a> event callback function.

### -field CLIENT_WriteGpioPins

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_write_pins">CLIENT_WriteGpioPins</a> event callback function.

### -field CLIENT_WriteGpioPinsUsingMask

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_write_pins_mask">CLIENT_WriteGpioPinsUsingMask</a> event callback function.

### -field CLIENT_SaveBankHardwareContext

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_save_bank_hardware_context">CLIENT_SaveBankHardwareContext</a> event callback function.

### -field CLIENT_RestoreBankHardwareContext

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_restore_bank_hardware_context">CLIENT_RestoreBankHardwareContext</a> event callback function.

### -field CLIENT_PreProcessControllerInterrupt

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_pre_process_controller_interrupt">CLIENT_PreProcessControllerInterrupt</a> event callback function.

### -field CLIENT_ControllerSpecificFunction

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_controller_specific_function">CLIENT_ControllerSpecificFunction</a> event callback function.

### -field CLIENT_ReconfigureInterrupt

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_reconfigure_interrupt">CLIENT_ReconfigureInterrupt</a> event callback function.

### -field CLIENT_QueryEnabledInterrupts

A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_enabled_interrupts">CLIENT_QueryEnabledInterrupts</a> event callback function. This member is supported starting with Windows 8.1.

### -field CLIENT_ConnectFunctionConfigPins

### -field CLIENT_DisconnectFunctionConfigPins

## -remarks

The GPIO controller driver passes a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure as an input parameter to the <a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method registers the driver to use the services provided by GpioClx. Typically, the driver calls this method from its <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine.

The <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure contains two unnamed unions. Each union can contain a pointer to one of two alternative types of event callback functions. In each case, your GPIO controller driver should implement the type of callback function that is best suited to the GPIO controller hardware. The GPIO controller driver's <i>CLIENT_QueryControllerBasicInformation</i> callback function informs GpioClx which callback functions are implemented.

After the GPIO controller driver calls <b>GPIO_CLX_RegisterClient</b> to register a set of callbacks, GpioClx calls the driver's <i>CLIENT_QueryControllerBasicInformation</i> callback function to obtain a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure that contains GPIO controller hardware attributes and configuration data. GpioClx uses this information to determine which callback functions the GPIO controller driver has implemented.

If the GPIO controller driver implements <i>CLIENT_ReadGpioPins</i> and <i>CLIENT_WriteGpioPins</i> callback functions, the <i>CLIENT_QueryControllerBasicInformation</i> callback function should set the <b>FormatIoRequestsAsMasks</b> flag bit in the <b>Flags</b> member of this <b>CLIENT_CONTROLLER_BASIC_INFORMATION</b> structure to 0.

If the <i>CLIENT_QueryControllerBasicInformation</i> callback function sets the <b>FormatIoRequestsAsMasks</b> flag bit to 1, this value indicates that the driver implements <i>CLIENT_ReadGpioPinsUsingMask</i> and <i>CLIENT_WriteGpioPinsUsingMask</i> callback functions.

GpioClx requires a GPIO controller driver to implement certain callback functions, but support for other callback functions is optional. For more information, see <a href="/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_clear_active_interrupts">CLIENT_ClearActiveInterrupts</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_connect_io_pins">CLIENT_ConnectIoPins</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_controller_specific_function">CLIENT_ControllerSpecificFunction</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disable_interrupt">CLIENT_DisableInterrupt</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disconnect_io_pins">CLIENT_DisconnectIoPins</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_mask_interrupts">CLIENT_MaskInterrupts</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_pre_process_controller_interrupt">CLIENT_PreProcessControllerInterrupt</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_prepare_controller">CLIENT_PrepareController</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_active_interrupts">CLIENT_QueryActiveInterrupts</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_enabled_interrupts">CLIENT_QueryEnabledInterrupts</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins">CLIENT_ReadGpioPins</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins_mask">CLIENT_ReadGpioPinsUsingMask</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_reconfigure_interrupt">CLIENT_ReconfigureInterrupt</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_release_controller">CLIENT_ReleaseController</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_restore_bank_hardware_context">CLIENT_RestoreBankHardwareContext</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_save_bank_hardware_context">CLIENT_SaveBankHardwareContext</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_start_controller">CLIENT_StartController</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_stop_controller">CLIENT_StopController</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_unmask_interrupt">CLIENT_UnmaskInterrupt</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_write_pins">CLIENT_WriteGpioPins</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_write_pins_mask">CLIENT_WriteGpioPinsUsingMask</a>



<a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>
