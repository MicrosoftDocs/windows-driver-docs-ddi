---
UID: NS:gpioclx._CLIENT_CONTROLLER_BASIC_INFORMATION
title: "_CLIENT_CONTROLLER_BASIC_INFORMATION"
author: windows-driver-content
description: The CLIENT_CONTROLLER_BASIC_INFORMATION structure contains general-purpose I/O (GPIO) controller hardware attributes and configuration information.
old-location: gpio\client_controller_basic_information.htm
tech.root: GPIO
ms.assetid: CE92249C-99B5-411E-B0D7-C1FF4824949E
ms.date: 2/15/2018
ms.keywords: "*PCLIENT_CONTROLLER_BASIC_INFORMATION, CLIENT_CONTROLLER_BASIC_INFORMATION, CLIENT_CONTROLLER_BASIC_INFORMATION structure [Parallel Ports], GPIO.client_controller_basic_information, PCLIENT_CONTROLLER_BASIC_INFORMATION, PCLIENT_CONTROLLER_BASIC_INFORMATION structure pointer [Parallel Ports], _CLIENT_CONTROLLER_BASIC_INFORMATION, gpioclx/CLIENT_CONTROLLER_BASIC_INFORMATION, gpioclx/PCLIENT_CONTROLLER_BASIC_INFORMATION"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_CONTROLLER_BASIC_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: CLIENT_CONTROLLER_BASIC_INFORMATION, *PCLIENT_CONTROLLER_BASIC_INFORMATION
---

# _CLIENT_CONTROLLER_BASIC_INFORMATION structure


## -description


The <b>CLIENT_CONTROLLER_BASIC_INFORMATION</b> structure contains general-purpose I/O (GPIO) controller hardware attributes and  configuration information.


## -struct-fields




### -field Version

The version number of this structure. Set this member to <b>GPIO_CONTROLLER_BASIC_INFORMATION_VERSION</b>, which is defined in the Gpioclx.h header file.


### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>CLIENT_CONTROLLER_BASIC_INFORMATION</b>).


### -field TotalPins

The number of pins on the GPIO controller. If the pins are partitioned into multiple banks, this member specifies the total pin count across all of the banks in the GPIO controller.


### -field NumberOfPinsPerBank

The number of GPIO pins for each bank. The maximum number of pins for each bank is 64. The pins on the GPIO controller are partitioned into one or more banks. Each bank contains the number of pins specified by this parameter, with the possible exception of the last bank. For more information, see Remarks.


### -field DeviceIdleTimeout

The idle time-out interval, in milliseconds, if the GPIO controller supports the D3 power state. The time-out interval is the minimum amount of time that a GPIO controller stays in the D0 state after the controller becomes idle. After the time-out interval expires, the power manager might request that the controller switch to the D3 state.


### -field Flags

A set of flags that specify the hardware attributes of the GPIO controller. This member can be set to all zeros or to any bitwise-OR combination of the following flag bits:

<ul>
<li><b>MemoryMappedController</b></li>
<li><b>ActiveInterruptsAutoClearOnRead</b></li>
<li><b>FormatIoRequestsAsMasks</b></li>
<li><b>DeviceIdlePowerMgmtSupported</b></li>
<li><b>BankIdlePowerMgmtSupported</b></li>
<li><b>EmulateDebouncing</b></li>
<li><b>EmulateActiveBoth</b></li>
</ul>
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function uses a <b>CLIENT_CONTROLLER_BASIC_INFORMATION</b> structure to pass device-specific information about a GPIO controller to the GPIO framework extension (GpioClx).

A GPIO controller driver can partition the pins in a GPIO controller device into some number of banks. If N is the number of banks in the controller, the banks are numbered 0 to N–1. All except the last bank (that is, bank number N–1) must contain the number of pins specified in the <b>NumberOfPinsPerBank</b> member. The last bank can have any number of pins from one to <b>NumberOfPinsPerBank</b>.

GpioClx determines the total number of banks in the GPIO controller from the values of the <b>TotalPins</b> and <b>NumberOfPinsPerBank</b> members. GpioClx uses the following integer formula to calculate the total number of banks:

<b>TotalPins</b>
<b>NumberOfPinsPerBank </b>
<b>NumberOfPinsPerBank</b>
Typically, a bank in a GPIO controller device can be turned on and off independently of the other banks in the same device. Thus, power can be saved by turning off a bank that is idle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>
 

 

