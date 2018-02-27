---
UID: NS:gpioclx._CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
title: "_CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT"
author: windows-driver-content
description: The CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure contains a set of general-purpose I/O (GPIO) controller attributes that were requested by the GPIO framework extension (GpioClx).
old-location: gpio\client_controller_query_set_information_output.htm
old-project: GPIO
ms.assetid: D145BAD6-EFE2-4B04-AF6E-F00486C78E8A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure [Parallel Ports], GPIO.client_controller_query_set_information_output, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure pointer [Parallel Ports], _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, gpioclx/CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, gpioclx/PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT"
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
-	CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
product: Windows
targetos: Windows
req.typenames: CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, *PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT
---

# _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure


## -description


The <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</b> structure contains a set of general-purpose I/O (GPIO) controller attributes that were requested by the GPIO framework extension (GpioClx).


## -syntax


````
typedef struct _CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT {
  USHORT Version;
  USHORT Size;
  union {
    CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT BankPowerInformation;
    struct {
      ULONG ResourceMapping[ANYSIZE_ARRAY];
    } BankInterruptBinding;
    struct {
      BOOLEAN Mapping[ANYSIZE_ARRAY];
    } ControllerFunctionBankMapping;
  };
} CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT, *PCLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT;
````


## -struct-fields




### -field Version

Specifies the version number of this structure.


### -field Size

Specifies the size, in bytes, of this structure.


### -field BankInterruptBinding

 


### -field BankInterruptBinding.ResourceMapping

 


### -field ControllerFunctionBankMapping

 


### -field ControllerFunctionBankMapping.Mapping

 




#### - ( unnamed union )

A union of members that contain output information for the various types of attribute requests. The <b>RequestType</b> member of the corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a> structure determines which of these members is used.



#### BankPowerInformation

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh698242">CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</a> structure that contains the power attributes of the GPIO bank that is identified by the <b>BankPowerInformation.BankId</b> member of the corresponding <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</b> structure.



#### BankInterruptBinding

A structure that contains information about the binding of interrupt resources to GPIO banks.



##### ResourceMapping

An array of interrupt resource numbers. The number of elements in the array equals the number of GPIO banks. If N is the number of banks in the GPIO controller, the banks are numbered 0 to N–1. Element 0 of the array contains the interrupt resource number that is bound to bank 0, element 1 contains the interrupt resource number that is bound to bank 1, and so on. No more than one interrupt resource can be bound to a GPIO bank, but two or more banks might share an interrupt resource. If a bank is not bound to an interrupt resource, the corresponding array element is set to <b>GPIO_BANK_INTERRUPT_BINDING_RESERVED_INDEX</b> (0xffff).

An interrupt resource is identified by its resource number, which is the index of the resource in the <b>ResourcesTranslated</b> or <b>ResourcesRaw</b> resource list in the <b>BankInterruptBinding</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a> structure. If a list contains M resources, the resources are numbered 0 to M-1. Only resource numbers that correspond to interrupt resources in the resource list can appear in the <b>ResourceMapping</b> array.



#### ControllerFunctionBankMapping

A structure that contains information about the GPIO banks that must be in the F0 (fully on) power state to handle an I/O control request (IOCTL).



##### Mapping

An array of BOOLEAN values that indicates the mapping of required F0 power states to GPIO banks. The number of elements in the array equals the number of GPIO banks. If N is the number of banks in the GPIO controller, the banks are numbered 0 to N–1. Element 0 of the array contains the mapping for bank 0, element 1 contains the mapping for bank 1, and so on. If an element is <b>TRUE</b>, the corresponding GPIO bank must be in the F0 power state to handle the IOCTL. If an element is <b>FALSE</b>, the corresponding bank is not required to be in the F0 power state.


## -remarks



The optional <i>OutputBuffer</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a> function is a pointer to a caller-allocated <b>CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT</b> structure. The function writes the requested attribute information to this structure, if <i>OutputBuffer</i> is non-NULL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698241">CLIENT_QuerySetControllerInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698238">CLIENT_CONTROLLER_QUERY_SET_INFORMATION_INPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698242">CLIENT_QUERY_BANK_POWER_INFORMATION_OUTPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_CONTROLLER_QUERY_SET_INFORMATION_OUTPUT structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

