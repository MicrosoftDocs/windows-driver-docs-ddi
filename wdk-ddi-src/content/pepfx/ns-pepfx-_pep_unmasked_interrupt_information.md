---
UID: NS:pepfx._PEP_UNMASKED_INTERRUPT_INFORMATION
title: _PEP_UNMASKED_INTERRUPT_INFORMATION (pepfx.h)
description: The PEP_UNMASKED_INTERRUPT_INFORMATION structure contains information about an interrupt source.
old-location: kernel\pep_unmasked_interrupt_information.htm
tech.root: kernel
ms.assetid: 1DD9A0A2-7D19-419A-8653-C16FDB28299E
ms.date: 04/30/2018
ms.keywords: "*PPEP_UNMASKED_INTERRUPT_INFORMATION, PEP_UNMASKED_INTERRUPT_INFORMATION, PEP_UNMASKED_INTERRUPT_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_UNMASKED_INTERRUPT_INFORMATION, PPEP_UNMASKED_INTERRUPT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_UNMASKED_INTERRUPT_INFORMATION, kernel.pep_unmasked_interrupt_information, pepfx/PEP_UNMASKED_INTERRUPT_INFORMATION, pepfx/PPEP_UNMASKED_INTERRUPT_INFORMATION"
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
api_name:
-	PEP_UNMASKED_INTERRUPT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PEP_UNMASKED_INTERRUPT_INFORMATION, *PPEP_UNMASKED_INTERRUPT_INFORMATION
---

# _PEP_UNMASKED_INTERRUPT_INFORMATION structure


## -description


The <b>PEP_UNMASKED_INTERRUPT_INFORMATION</b> structure contains information about an interrupt source.


## -struct-fields




### -field Version

The version of this structure.


### -field Size

The size, in bytes, of this structure.


### -field Flags

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt629127">PEP_UNMASKED_INTERRUPT_FLAGS</a> union that indicates whether the interrupt is a primary or secondary interrupt. For more information, see <a href="https://msdn.microsoft.com/731B0E36-4480-4B69-931E-1F7B40B18911">Primary and Secondary Interrupts</a>.


### -field Mode

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a> enumeration value. This member indicates whether the interrupt is edge-triggered or level-triggered.


### -field Polarity

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff554243">KINTERRUPT_POLARITY</a> enumeration value. This member indicates which edge or level of the interrupt signal triggers the interrupt.


### -field Gsiv

The global system interrupt vector (GSIV) number that identifies this interrupt. The ACPI firmware assigns GSIV numbers to all primary interrupt lines. For secondary (GPIO) interrupt lines, the GSIV number is dynamically assigned by the operating system.


### -field PinNumber

For secondary interrupt sources, this member identifies the number of the pin on the general-purpose I/O (GPIO) controller that is connected to the interrupt signal line from the interrupting device. For primary interrupt sources, this member is undefined.

If a GPIO controller has N GPIO pins, the pins are numbered 0 to N–1. One or more of these GPIO pins might be configured as interrupt inputs.


### -field DeviceHandle

For secondary interrupt sources, this member contains the PEP device handle for the GPIO controller that is the source for this interrupt. For primary interrupt sources, this field is undefined.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a> callback routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186632">EnumerateInterruptSource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554239">KINTERRUPT_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554243">KINTERRUPT_POLARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629127">PEP_UNMASKED_INTERRUPT_FLAGS</a>
 

 

