---
UID: NS:pepfx._PEP_ACPI_INTERRUPT_RESOURCE
title: _PEP_ACPI_INTERRUPT_RESOURCE (pepfx.h)
description: The PEP_ACPI_INTERRUPT_RESOURCE structure describes an ACPI interrupt resource.
old-location: kernel\pep_acpi_interrupt_resource.htm
tech.root: kernel
ms.assetid: B440AB0E-72CC-40F1-B77E-C12C84124737
ms.date: 04/30/2018
keywords: ["_PEP_ACPI_INTERRUPT_RESOURCE structure"]
ms.keywords: "*PPEP_ACPI_INTERRUPT_RESOURCE, PEP_ACPI_INTERRUPT_RESOURCE, PEP_ACPI_INTERRUPT_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_INTERRUPT_RESOURCE, PPEP_ACPI_INTERRUPT_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_INTERRUPT_RESOURCE, kernel.pep_acpi_interrupt_resource, pepfx/PEP_ACPI_INTERRUPT_RESOURCE, pepfx/PPEP_ACPI_INTERRUPT_RESOURCE"
f1_keywords:
 - "pepfx/PEP_ACPI_INTERRUPT_RESOURCE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_ACPI_INTERRUPT_RESOURCE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_INTERRUPT_RESOURCE, *PPEP_ACPI_INTERRUPT_RESOURCE
---

# _PEP_ACPI_INTERRUPT_RESOURCE structure


## -description


The <b>PEP_ACPI_INTERRUPT_RESOURCE</b> structure describes an ACPI interrupt resource.


## -struct-fields




### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a> enumeration value describing this resource.


### -field InterruptType

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a> enumeration value that identifies the interrupt type.


### -field InterruptPolarity

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a> enumeration value that identifies how a device signals an interrupt request on an interrupt line.


### -field Flags

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a> structure that describes the capabilities of this ACPI resource.


### -field Count

The count of items in the <b>Pins</b> array.


### -field Pins

A list of pin numbers on the resource that are described by this descriptor. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a>
 

 

