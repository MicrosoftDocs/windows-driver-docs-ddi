---
UID: NS:wdm._IO_INTERRUPT_MESSAGE_INFO_ENTRY
title: _IO_INTERRUPT_MESSAGE_INFO_ENTRY (wdm.h)
description: The IO_INTERRUPT_MESSAGE_INFO_ENTRY structure describes the properties of a single message-signaled interrupt.
old-location: kernel\io_interrupt_message_info_entry.htm
tech.root: kernel
ms.assetid: e5007381-2436-4eb6-85cd-7145361ab793
ms.date: 04/30/2018
keywords: ["_IO_INTERRUPT_MESSAGE_INFO_ENTRY structure"]
ms.keywords: "*PIO_INTERRUPT_MESSAGE_INFO_ENTRY, IO_INTERRUPT_MESSAGE_INFO_ENTRY, IO_INTERRUPT_MESSAGE_INFO_ENTRY structure [Kernel-Mode Driver Architecture], PIO_INTERRUPT_MESSAGE_INFO_ENTRY, PIO_INTERRUPT_MESSAGE_INFO_ENTRY structure pointer [Kernel-Mode Driver Architecture], _IO_INTERRUPT_MESSAGE_INFO_ENTRY, kernel.io_interrupt_message_info_entry, kstruct_b_eb31dbfa-458d-47c4-b1df-96c315bd3ff6.xml, wdm/IO_INTERRUPT_MESSAGE_INFO_ENTRY, wdm/PIO_INTERRUPT_MESSAGE_INFO_ENTRY"
f1_keywords:
 - "wdm/IO_INTERRUPT_MESSAGE_INFO_ENTRY"
 - "IO_INTERRUPT_MESSAGE_INFO_ENTRY"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IO_INTERRUPT_MESSAGE_INFO_ENTRY
targetos: Windows
req.typenames: IO_INTERRUPT_MESSAGE_INFO_ENTRY, *PIO_INTERRUPT_MESSAGE_INFO_ENTRY
---

# _IO_INTERRUPT_MESSAGE_INFO_ENTRY structure


## -description


The <b>IO_INTERRUPT_MESSAGE_INFO_ENTRY</b> structure describes the properties of a single message-signaled interrupt.


## -struct-fields




### -field MessageAddress

Specifies the physical address that triggers the interrupt message.


### -field TargetProcessorSet

Specifies a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value that determines the set of processors that can receive the interrupt.


### -field InterruptObject

Pointer to the interrupt object that represents the interrupt. 


### -field MessageData

Specifies the value to be written to the address specified by <b>MessageAddress</b> to trigger the interrupt.


### -field Vector

Specifies the interrupt vector for the interrupt. 


### -field Irql

Specifies the device IRQL (DIRQL) for the interrupt. 


### -field Mode

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a> value that determines whether the interrupt is level-sensitive or latched. 


### -field Polarity

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a> value that determines whether the interrupt is active-high or active-low. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>
 

 

