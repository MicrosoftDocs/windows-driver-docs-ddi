---
UID: NE:storport._INTERRUPT_SYNCHRONIZATION_MODE
title: _INTERRUPT_SYNCHRONIZATION_MODE (storport.h)
description: The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.
old-location: storage\interrupt_synchronization_mode.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["INTERRUPT_SYNCHRONIZATION_MODE enumeration"]
ms.keywords: INTERRUPT_SYNCHRONIZATION_MODE, INTERRUPT_SYNCHRONIZATION_MODE enumeration [Storage Devices], InterruptSupportNone, InterruptSynchronizeAll, InterruptSynchronizePerMessage, _INTERRUPT_SYNCHRONIZATION_MODE, storage.interrupt_synchronization_mode, storport/INTERRUPT_SYNCHRONIZATION_MODE, storport/InterruptSupportNone, storport/InterruptSynchronizeAll, storport/InterruptSynchronizePerMessage, structs-storport_036aa424-5b04-4bf5-8418-8da008834c5b.xml
req.header: storport.h
req.include-header: Storport.h
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
req.typenames: INTERRUPT_SYNCHRONIZATION_MODE
f1_keywords:
 - _INTERRUPT_SYNCHRONIZATION_MODE
 - storport/_INTERRUPT_SYNCHRONIZATION_MODE
 - INTERRUPT_SYNCHRONIZATION_MODE
 - storport/INTERRUPT_SYNCHRONIZATION_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - INTERRUPT_SYNCHRONIZATION_MODE
---

# _INTERRUPT_SYNCHRONIZATION_MODE enumeration


## -description

The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.

## -enum-fields

### -field InterruptSupportNone

MSI interrupts are not supported.

### -field InterruptSynchronizeAll

The Storport driver serializes all message signaled interrupts using a single interrupt spin lock. When an interrupt occurs, the Storport driver calls the miniport driver's [**HwMSInterruptRoutine**](nc-storport-hw_message_signaled_interrupt_routine.md) routine at DIRQL after acquiring the interrupt spin lock.

### -field InterruptSynchronizePerMessage

The miniport driver serializes message signaled interrupts on a per message basis. In the synchronization per message mode, the Storport driver calls the miniport driver's [**HwMSInterruptRoutine**](nc-storport-hw_message_signaled_interrupt_routine.md) routine at DIRQL   holding the interrupt spin lock of the corresponding  message. For more on the behavior of this synchronization mode, see the remarks section for HwMSInterruptRoutine.

## -remarks

Miniport drivers define the HBA's interrupt synchronization mode by assigning one of the INTERRUPT_SYNCHRONIZATION_MODE enumeration values to the **InterruptSynchronizationMode** member of the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure.

## -see-also

[**HwMSInterruptRoutine**](nc-storport-hw_message_signaled_interrupt_routine.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**StorPortAcquireMSISpinLock**](nf-storport-storportacquiremsispinlock.md)

[**StorPortReleaseMSISpinLock**](nf-storport-storportreleasemsispinlock.md)

