---
UID: NE:gpioclx._CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE
title: "_CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE"
author: windows-driver-content
description: The CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE enumeration type indicates what type of attribute information the GPIO framework extension (GpioClx) is requesting from the GPIO controller driver.
old-location: gpio\client_controller_query_set_request_type.htm
old-project: GPIO
ms.assetid: 050752CC-FBD6-4EB1-A17F-53C5C569E3FB
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE, CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE, CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE enumeration [Parallel Ports], GPIO.client_controller_query_set_request_type, QueryBankInterruptBindingInformation, QueryBankPowerInformation, QueryControllerFunctionBankMappingInformation, QuerySetRequestMaximumType, _CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE, gpioclx/CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE, gpioclx/QueryBankInterruptBindingInformation, gpioclx/QueryBankPowerInformation, gpioclx/QueryControllerFunctionBankMappingInformation, gpioclx/QuerySetRequestMaximumType"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE, *PCLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE
---

# _CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE enumeration


## -description


The <b>CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</b> enumeration type indicates what type of attribute information the GPIO framework extension (GpioClx) is requesting from the GPIO controller driver.


## -syntax


````
typedef enum _CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE { 
  QueryBankPowerInformation,
  QueryBankInterruptBindingInformation,
  QueryControllerFunctionBankMappingInformation,
  QuerySetRequestMaximumType
} CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE;
````


## -enum-fields




### -field QueryBankPowerInformation

Power attributes. For this attribute type, the <b>BankPowerInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a> structure specifies a GPIO bank, and the <b>BankPowerInformation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a> structure contains the power attributes of the specified bank.


### -field QueryBankInterruptBindingInformation

Interrupt-binding attributes. For this attribute type, the <b>BankInterruptBinding</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure contains the raw and translated hardware resources assigned to the GPIO controller, and the <b>BankInterruptBinding</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</b> structure describes the binding of interrupt resources to GPIO banks.


### -field QueryControllerFunctionBankMappingInformation

Function-mapping attributes. For this attribute type, the <b>ControllerFunctionBankMapping</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure specifies an I/O control request (IOCTL), and the <b>ControllerFunctionBankMapping</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</b> structure indicates which GPIO banks must be in the F0 (fully on) power state to handle the specified IOCTL.


### -field QuerySetRequestMaximumType

Reserved for use by the operating system.


## -remarks



The <b>RequestType</b> member of the <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure is a value of type <b>CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</b>. GpioClx sets this member to a  <b>CLIENT_CONTROLLER_QUERY_SET_REQUEST_TYPE</b> enumeration constant to indicate what type of attribute information is requested. The <a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a> callback function takes a pointer to a <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure as an input parameter, and optionally takes a pointer to a <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</b> structure as an output parameter.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698239">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a>



 

 


