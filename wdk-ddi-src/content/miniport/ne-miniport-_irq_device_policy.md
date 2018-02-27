---
UID: NE:miniport._IRQ_DEVICE_POLICY
title: "_IRQ_DEVICE_POLICY"
author: windows-driver-content
description: The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.
old-location: kernel\irq_device_policy.htm
old-project: kernel
ms.assetid: 1a605eed-d9a1-4a2f-a095-3e790061527b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PIRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY enumeration [Kernel-Mode Driver Architecture], IrqPolicyAllCloseProcessors, IrqPolicyAllProcessorsInMachine, IrqPolicyMachineDefault, IrqPolicyOneCloseProcessor, IrqPolicySpecifiedProcessors, IrqPolicySpreadMessagesAcrossAllProcessors, PIRQ_DEVICE_POLICY, PIRQ_DEVICE_POLICY enumeration pointer [Kernel-Mode Driver Architecture], _IRQ_DEVICE_POLICY, kernel.irq_device_policy, sysenum_09bcf230-5558-447e-8646-c60d807365d4.xml, wdm/IRQ_DEVICE_POLICY, wdm/IrqPolicyAllCloseProcessors, wdm/IrqPolicyAllProcessorsInMachine, wdm/IrqPolicyMachineDefault, wdm/IrqPolicyOneCloseProcessor, wdm/IrqPolicySpecifiedProcessors, wdm/IrqPolicySpreadMessagesAcrossAllProcessors, wdm/PIRQ_DEVICE_POLICY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IRQ_DEVICE_POLICY
product: Windows
targetos: Windows
req.typenames: IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY
---

# _IRQ_DEVICE_POLICY enumeration


## -description


The <b>IRQ_DEVICE_POLICY</b> enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.


## -syntax


````
typedef enum _IRQ_DEVICE_POLICY { 
  IrqPolicyMachineDefault                     = 0,
  IrqPolicyAllCloseProcessors                 = 1,
  IrqPolicyOneCloseProcessor                  = 2,
  IrqPolicyAllProcessorsInMachine             = 3,
  IrqPolicySpecifiedProcessors                = 4,
  IrqPolicySpreadMessagesAcrossAllProcessors  = 5
} IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY;
````


## -enum-fields




### -field IrqPolicyMachineDefault

The device does not require any particular assignment of interrupts to processors.


### -field IrqPolicyAllCloseProcessors

The operating system should assign interrupts from the device to processors that are close to the device. On non-NUMA computers, the effect of this value is identical to that of <b>IrqPolicyAllProcessorsInMachine</b>.


### -field IrqPolicyOneCloseProcessor

The operating system should assign a single interrupt for the device to one processor that is close to the device. On non-NUMA computers, the operating system can assign the interrupt to any processor.


### -field IrqPolicyAllProcessorsInMachine

The operating system should assign interrupts from the device to all processors.


### -field IrqPolicySpecifiedProcessors

The operating system should assign interrupts from the device to a specific set of processors.


### -field IrqPolicySpreadMessagesAcrossAllProcessors

The operating system should assign different message-signaled interrupts to different processors, if possible. 


### -field IrqPolicyAllProcessorsInMachineWhenSteered




## -remarks



The <b>Interrupt.AffinityPolicy</b> member of the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure is an <b>IRQ_DEVICE_POLICY</b> enumeration value.




## -see-also

<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IRQ_DEVICE_POLICY enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

