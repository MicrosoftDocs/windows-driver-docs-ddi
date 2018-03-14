---
UID: NS:gpioclx._GPIO_CLIENT_REGISTRATION_PACKET
title: "_GPIO_CLIENT_REGISTRATION_PACKET"
author: windows-driver-content
description: The GPIO_CLIENT_REGISTRATION_PACKET structure contains registration information that the general-purpose I/O (GPIO) controller driver passes to the GPIO framework extension (GpioClx).
old-location: gpio\gpio_client_registration_packet.htm
old-project: GPIO
ms.assetid: A3E1FC46-ED09-4AB3-B898-253552A76649
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_CLIENT_REGISTRATION_PACKET, GPIO.gpio_client_registration_packet, GPIO_CLIENT_REGISTRATION_PACKET, GPIO_CLIENT_REGISTRATION_PACKET structure [Parallel Ports], PGPIO_CLIENT_REGISTRATION_PACKET, PGPIO_CLIENT_REGISTRATION_PACKET structure pointer [Parallel Ports], _GPIO_CLIENT_REGISTRATION_PACKET, gpioclx/GPIO_CLIENT_REGISTRATION_PACKET, gpioclx/PGPIO_CLIENT_REGISTRATION_PACKET"
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
-	GPIO_CLIENT_REGISTRATION_PACKET
product: Windows
targetos: Windows
req.typenames: GPIO_CLIENT_REGISTRATION_PACKET, *PGPIO_CLIENT_REGISTRATION_PACKET
---

# _GPIO_CLIENT_REGISTRATION_PACKET structure


## -description


The <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure contains registration information that the general-purpose I/O (GPIO) controller driver passes to the GPIO framework extension (GpioClx).


## -syntax


````
typedef struct _GPIO_CLIENT_REGISTRATION_PACKET {
  USHORT                                          Version;
  USHORT                                          Size;
  ULONG                                           Flags;
  ULONG                                           ControllerContextSize;
  ULONG64                                         Reserved;
  PGPIO_CLIENT_PREPARE_CONTROLLER                 CLIENT_PrepareController;
  PGPIO_CLIENT_RELEASE_CONTROLLER                 CLIENT_ReleaseController;
  PGPIO_CLIENT_START_CONTROLLER                   CLIENT_StartController;
  PGPIO_CLIENT_STOP_CONTROLLER                    CLIENT_StopController;
  PGPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION CLIENT_QueryControllerBasicInformation;
  PGPIO_CLIENT_QUERY_SET_CONTROLLER_INFORMATION   CLIENT_QuerySetControllerInformation;
  PGPIO_CLIENT_ENABLE_INTERRUPT                   CLIENT_EnableInterrupt;
  PGPIO_CLIENT_DISABLE_INTERRUPT                  CLIENT_DisableInterrupt;
  PGPIO_CLIENT_UNMASK_INTERRUPT                   CLIENT_UnmaskInterrupt;
  PGPIO_CLIENT_MASK_INTERRUPTS                    CLIENT_MaskInterrupts;
  PGPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS            CLIENT_QueryActiveInterrupts;
  PGPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS            CLIENT_ClearActiveInterrupts;
  PGPIO_CLIENT_CONNECT_IO_PINS                    CLIENT_ConnectIoPins;
  PGPIO_CLIENT_DISCONNECT_IO_PINS                 CLIENT_DisconnectIoPins;
  union {
    PGPIO_CLIENT_READ_PINS      CLIENT_ReadGpioPins;
    PGPIO_CLIENT_READ_PINS_MASK CLIENT_ReadGpioPinsUsingMask;
  };
  union {
    PGPIO_CLIENT_WRITE_PINS      CLIENT_WriteGpioPins;
    PGPIO_CLIENT_WRITE_PINS_MASK CLIENT_WriteGpioPinsUsingMask;
  };
  PGPIO_CLIENT_SAVE_BANK_HARDWARE_CONTEXT         CLIENT_SaveBankHardwareContext;
  PGPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT      CLIENT_RestoreBankHardwareContext;
  PGPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT   CLIENT_PreProcessControllerInterrupt;
  PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION       CLIENT_ControllerSpecificFunction;
  PGPIO_CLIENT_RECONFIGURE_INTERRUPT              CLIENT_ReconfigureInterrupt;
  PGPIO_CLIENT_QUERY_ENABLED_INTERRUPTS           CLIENT_QueryEnabledInterrupts;
} GPIO_CLIENT_REGISTRATION_PACKET, *PGPIO_CLIENT_REGISTRATION_PACKET;
````


## -struct-fields




### -field Version

The version number for the GPIO interface that the GPIO controller driver supports. Set this member to the value GPIO_CLIENT_VERSION, which is defined in the Gpioclx.h header file.


### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>GPIO_CLIENT_REGISTRATION_PACKET</b>).


### -field Flags

A set of flags that indicate which registration options are selected. No flags are currently defined for registration options. Set this member to zero.


### -field ControllerContextSize

The required device context size, in bytes. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method allocates a device context of this size. When GpioClx calls any registered callback function in the <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure, GpioClx passes this device context to the callback function as a parameter. The callback functions use this context to access and update the driver's information about the state of the GPIO controller device. For more information, see <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">GPIO Device Contexts</a>.


### -field Reserved

Reserved for future use. Set this member to zero.


### -field CLIENT_PrepareController

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439389">CLIENT_PrepareController</a> event callback function.


### -field CLIENT_ReleaseController

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439411">CLIENT_ReleaseController</a> event callback function.


### -field CLIENT_StartController

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439424">CLIENT_StartController</a> event callback function.


### -field CLIENT_StopController

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439430">CLIENT_StopController</a> event callback function.


### -field CLIENT_QueryControllerBasicInformation

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function.


### -field CLIENT_QuerySetControllerInformation

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a> event callback function.


### -field CLIENT_EnableInterrupt

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a> event callback function.


### -field CLIENT_DisableInterrupt

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a> event callback function.


### -field CLIENT_UnmaskInterrupt

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439435">CLIENT_UnmaskInterrupt</a> event callback function.


### -field CLIENT_MaskInterrupts

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439380">CLIENT_MaskInterrupts</a> event callback function.


### -field CLIENT_QueryActiveInterrupts

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a> event callback function.


### -field CLIENT_ClearActiveInterrupts

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439341">CLIENT_ClearActiveInterrupts</a> event callback function.


### -field CLIENT_ConnectIoPins

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439347">CLIENT_ConnectIoPins</a> event callback function.


### -field CLIENT_DisconnectIoPins

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439374">CLIENT_DisconnectIoPins</a> event callback function.


### -field CLIENT_SaveBankHardwareContext

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a> event callback function.


### -field CLIENT_RestoreBankHardwareContext

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a> event callback function.


### -field CLIENT_PreProcessControllerInterrupt

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439392">CLIENT_PreProcessControllerInterrupt</a> event callback function.


### -field CLIENT_ControllerSpecificFunction

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh698237">CLIENT_ControllerSpecificFunction</a> event callback function.


### -field CLIENT_ReconfigureInterrupt

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a> event callback function.


### -field CLIENT_QueryEnabledInterrupts

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a> event callback function. This member is supported starting with Windows 8.1.


### -field CLIENT_ConnectFunctionConfigPins

 


### -field CLIENT_DisconnectFunctionConfigPins

 




#### - CLIENT_ReadGpioPins

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a> event callback function.


#### - CLIENT_ReadGpioPinsUsingMask

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a> event callback function.


#### - CLIENT_WriteGpioPins

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a> event callback function.


#### - CLIENT_WriteGpioPinsUsingMask

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a> event callback function.


## -remarks



The GPIO controller driver passes a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method registers the driver to use the services provided by GpioClx. Typically, the driver calls this method from its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine.

The <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure contains two unnamed unions. Each union can contain a pointer to one of two alternative types of event callback functions. In each case, your GPIO controller driver should implement the type of callback function that is best suited to the GPIO controller hardware. The GPIO controller driver's <i>CLIENT_QueryControllerBasicInformation</i> callback function informs GpioClx which callback functions are implemented.

After the GPIO controller driver calls <b>GPIO_CLX_RegisterClient</b> to register a set of callbacks, GpioClx calls the driver's <i>CLIENT_QueryControllerBasicInformation</i> callback function to obtain a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure that contains GPIO controller hardware attributes and configuration data. GpioClx uses this information to determine which callback functions the GPIO controller driver has implemented.

If the GPIO controller driver implements <i>CLIENT_ReadGpioPins</i> and <i>CLIENT_WriteGpioPins</i> callback functions, the <i>CLIENT_QueryControllerBasicInformation</i> callback function should set the <b>FormatIoRequestsAsMasks</b> flag bit in the <b>Flags</b> member of this <b>CLIENT_CONTROLLER_BASIC_INFORMATION</b> structure to 0.

If the <i>CLIENT_QueryControllerBasicInformation</i> callback function sets the <b>FormatIoRequestsAsMasks</b> flag bit to 1, this value indicates that the driver implements <i>CLIENT_ReadGpioPinsUsingMask</i> and <i>CLIENT_WriteGpioPinsUsingMask</i> callback functions.

GpioClx requires a GPIO controller driver to implement certain callback functions, but support for other callback functions is optional. For more information, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439347">CLIENT_ConnectIoPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439411">CLIENT_ReleaseController</a>



<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439414">CLIENT_RestoreBankHardwareContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439430">CLIENT_StopController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439419">CLIENT_SaveBankHardwareContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698237">CLIENT_ControllerSpecificFunction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439374">CLIENT_DisconnectIoPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439392">CLIENT_PreProcessControllerInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439341">CLIENT_ClearActiveInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439424">CLIENT_StartController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439435">CLIENT_UnmaskInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439380">CLIENT_MaskInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439389">CLIENT_PrepareController</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLIENT_REGISTRATION_PACKET structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

