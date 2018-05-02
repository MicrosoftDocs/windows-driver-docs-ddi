---
UID: NS:gpioclx._CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
title: "_CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT"
author: windows-driver-content
description: The CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure contains a request for the hardware attributes of the general-purpose I/O (GPIO) controller.
old-location: gpio\client_controller_query_set_information_input.htm
old-project: GPIO
ms.assetid: C4AA60FF-03AD-444F-B897-654B787B5F86
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure [Parallel Ports], GPIO.client_controller_query_set_information_input, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure pointer [Parallel Ports], _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
product:
- Windows
targetos: Windows
req.typenames: CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT, *PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT
---

# _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT structure


## -description


The <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure contains a request for the hardware attributes of the general-purpose I/O (GPIO) controller.


## -struct-fields




### -field RequestType

The type of attribute information that is being requested. This member is set to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698240">CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</a> enumeration value.


### -field Size

Specifies the size, in bytes, of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure.


### -field Flags

A set of flag bits that supply additional information about the type of attribute request indicated by the <b>RequestType</b> member. No flags are currently defined for the <b>Flags</b> member.


### -field BankPowerInformation

 


### -field BankPowerInformation.BankId

 


### -field BankInterruptBinding

 


### -field BankInterruptBinding.ResourcesTranslated

 


### -field BankInterruptBinding.ResourcesRaw

 


### -field BankInterruptBinding.TotalBanks

 


### -field ControllerFunctionBankMapping

 


### -field ControllerFunctionBankMapping.InputBuffer

 


### -field ControllerFunctionBankMapping.InputBufferSize

 


### -field ControllerFunctionBankMapping.OutputBufferSize

 


### -field ControllerFunctionBankMapping.TotalBanks

 




#### - ( unnamed union )

A union of members that contain input information for the various types of attribute requests. The <b>RequestType</b> member determines which member of this union is used. The following table shows the union member that corresponds to each valid <b>RequestType</b> value.

<table>
<tr>
<th><b>RequestType</b> value</th>
<th>Union member</th>
</tr>
<tr>
<td><b>QueryBankPowerInformation</b></td>
<td><b>BankPowerInformation</b></td>
</tr>
<tr>
<td><b>QueryBankInterruptBindingInformation</b></td>
<td><b>BankInterruptBinding</b></td>
</tr>
<tr>
<td><b>QueryControllerFunctionBankMappingInformation</b></td>
<td><b>ControllerFunctionBankMapping</b></td>
</tr>
</table>
 



#### BankPowerInformation

A structure that contains information about the GPIO bank whose power attributes are being requested.



##### BankId

The identifier for a bank of GPIO pins. If M is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to M–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.



#### BankInterruptBinding

A structure that contains information about the interrupt resources that are assigned to the GPIO controller.



##### ResourcesTranslated

A handle to a framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.



##### ResourcesRaw

A handle to a framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.



##### TotalBanks

The number of banks in the GPIO controller. This member indicates the expected length of the <b>BankInterruptBinding.ResourceMapping</b> array in the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure, if the caller supplies a non-NULL pointer to this structure.



#### ControllerFunctionBankMapping

A structure that contains information about an I/O control request (IOCTL).



##### InputBuffer

A pointer to the input buffer for the IOCTL.



##### InputBufferSize

The size, in bytes, of the input buffer for the IOCTL.



##### OutputBufferSize

The size, in bytes, of the output buffer for the IOCTL.



##### TotalBanks

The number of banks in the GPIO controller. This member indicates the expected length of the <b>ControllerFunctionBankMapping.Mapping</b> array in the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure, if the caller supplies a non-NULL pointer to this structure.


## -remarks



The <i>InputBuffer</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a> function is a pointer to a <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a>
 

 

