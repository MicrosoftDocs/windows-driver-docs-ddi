---
UID: NE:wdm._IRQ_DEVICE_POLICY
title: _IRQ_DEVICE_POLICY (wdm.h)
description: The _IRQ_DEVICE_POLICY enumeration (wdm.h) type indicates the operating system policy used to assign interrupts from a device to different processors.
old-location: kernel\irq_device_policy.htm
tech.root: kernel
ms.date: 09/16/2022
keywords: ["IRQ_DEVICE_POLICY enumeration"]
ms.keywords: "*PIRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY, IRQ_DEVICE_POLICY enumeration [Kernel-Mode Driver Architecture], IrqPolicyAllCloseProcessors, IrqPolicyAllProcessorsInMachine, IrqPolicyMachineDefault, IrqPolicyOneCloseProcessor, IrqPolicySpecifiedProcessors, IrqPolicySpreadMessagesAcrossAllProcessors, PIRQ_DEVICE_POLICY, PIRQ_DEVICE_POLICY enumeration pointer [Kernel-Mode Driver Architecture], _IRQ_DEVICE_POLICY, kernel.irq_device_policy, sysenum_09bcf230-5558-447e-8646-c60d807365d4.xml, wdm/IRQ_DEVICE_POLICY, wdm/IrqPolicyAllCloseProcessors, wdm/IrqPolicyAllProcessorsInMachine, wdm/IrqPolicyMachineDefault, wdm/IrqPolicyOneCloseProcessor, wdm/IrqPolicySpecifiedProcessors, wdm/IrqPolicySpreadMessagesAcrossAllProcessors, wdm/PIRQ_DEVICE_POLICY"
req.header: wdm.h
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
targetos: Windows
req.typenames: IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY
f1_keywords:
 - _IRQ_DEVICE_POLICY
 - wdm/_IRQ_DEVICE_POLICY
 - PIRQ_DEVICE_POLICY
 - wdm/PIRQ_DEVICE_POLICY
 - IRQ_DEVICE_POLICY
 - wdm/IRQ_DEVICE_POLICY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _IRQ_DEVICE_POLICY
 - PIRQ_DEVICE_POLICY
 - IRQ_DEVICE_POLICY
---

# _IRQ_DEVICE_POLICY enumeration (wdm.h)

## -description

The **IRQ_DEVICE_POLICY** enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.

## -enum-fields

### -field IrqPolicyMachineDefault:0

The device does not require any particular assignment of interrupts to processors.

### -field IrqPolicyAllCloseProcessors:1

The operating system should assign interrupts from the device to processors that are close to the device. On non-NUMA computers, the effect of this value is identical to that of **IrqPolicyAllProcessorsInMachine**.

### -field IrqPolicyOneCloseProcessor:2

The operating system should assign a single interrupt for the device to one processor that is close to the device. On non-NUMA computers, the operating system can assign the interrupt to any processor.

### -field IrqPolicyAllProcessorsInMachine:3

The operating system should assign interrupts from the device to all processors.

### -field IrqPolicySpecifiedProcessors:4

The operating system should assign interrupts from the device to a specific set of processors.

### -field IrqPolicySpreadMessagesAcrossAllProcessors:5

The operating system should assign different message-signaled interrupts to different processors, if possible.

### -field IrqPolicyAllProcessorsInMachineWhenSteered:6

Reserved for system use. Do not use in your driver.

## -remarks

The **Interrupt.AffinityPolicy** member of the [IO_RESOURCE_DESCRIPTOR](./ns-wdm-_io_resource_descriptor.md) structure is an **IRQ_DEVICE_POLICY** enumeration value.

## -see-also

- [IO_RESOURCE_DESCRIPTOR](./ns-wdm-_io_resource_descriptor.md)
