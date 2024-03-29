---
UID: NS:pep_x._PEP_ACPI_IO_MEMORY_RESOURCE
title: _PEP_ACPI_IO_MEMORY_RESOURCE (pep_x.h)
description: Learn how the PEP_ACPI_IO_MEMORY_RESOURCE structure describes an ACPI IO port descriptor resource.
old-location: kernel\pep_acpi_io_memory_resource.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_ACPI_IO_MEMORY_RESOURCE structure"]
ms.keywords: "*PPEP_ACPI_IO_MEMORY_RESOURCE, PEP_ACPI_IO_MEMORY_RESOURCE, PEP_ACPI_IO_MEMORY_RESOURCE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_IO_MEMORY_RESOURCE, PPEP_ACPI_IO_MEMORY_RESOURCE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_IO_MEMORY_RESOURCE, kernel.pep_acpi_io_memory_resource, pepfx/PEP_ACPI_IO_MEMORY_RESOURCE, pepfx/PPEP_ACPI_IO_MEMORY_RESOURCE"
req.header: pep_x.h
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
targetos: Windows
req.typenames: PEP_ACPI_IO_MEMORY_RESOURCE, *PPEP_ACPI_IO_MEMORY_RESOURCE
f1_keywords:
 - _PEP_ACPI_IO_MEMORY_RESOURCE
 - pep_x/_PEP_ACPI_IO_MEMORY_RESOURCE
 - PPEP_ACPI_IO_MEMORY_RESOURCE
 - pep_x/PPEP_ACPI_IO_MEMORY_RESOURCE
 - PEP_ACPI_IO_MEMORY_RESOURCE
 - pep_x/PEP_ACPI_IO_MEMORY_RESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_ACPI_IO_MEMORY_RESOURCE
 - PPEP_ACPI_IO_MEMORY_RESOURCE
 - PEP_ACPI_IO_MEMORY_RESOURCE
---

# _PEP_ACPI_IO_MEMORY_RESOURCE structure (pep_x.h)


## -description

The <b>PEP_ACPI_IO_MEMORY_RESOURCE</b> structure describes an ACPI IO port descriptor resource.

## -struct-fields

### -field Type

A <a href="/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a> enumeration value that identifies the resource type for this ACPI resource.

### -field Information

If bit 0 is a 1, this indicates that the logical device decodes 16-bit addresses. If bit 0 is 0, this indicates that the logical device only decodes the first 10 bits of the address.

Bits 1 to 7 of this member are reserved and must be set to zero.

### -field MinimumAddress

Specifies the minimum acceptable starting address for the IO range.

### -field MaximumAddress

Specifies the maximum acceptable starting address for the IO range.

### -field Alignment

Specifies the alignment granularity for the IO address assigned.

### -field Length

Specifies the number of bytes in the IO range.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ne-pepfx-_pep_acpi_resource_type">PEP_ACPI_RESOURCE_TYPE</a>

