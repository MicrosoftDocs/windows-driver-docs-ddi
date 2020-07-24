---
UID: NF:pep_x.PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
title: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function (pep_x.h)
description: The PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function initializes a platform extension plug-in's (PEP) PEP_ACPI_IO_MEMORY_RESOURCE structure.
old-location: kernel\pep_acpi_initialize_ioport_resource.htm
tech.root: kernel
ms.assetid: E7F9F8EF-3FDC-41D9-BB89-9EB93ED1A504
ms.date: 04/30/2018
keywords: ["PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function"]
ms.keywords: PEP_ACPI_INITIALIZE_IOPORT_RESOURCE, PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function [Kernel-Mode Driver Architecture], kernel.pep_acpi_initialize_ioport_resource, pepfx/PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
f1_keywords:
 - "pep_x/PEP_ACPI_INITIALIZE_IOPORT_RESOURCE"
 - "PEP_ACPI_INITIALIZE_IOPORT_RESOURCE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_ACPI_INITIALIZE_IOPORT_RESOURCE
targetos: Windows
req.typenames: 
---

# PEP_ACPI_INITIALIZE_IOPORT_RESOURCE function


## -description


The <b>PEP_ACPI_INITIALIZE_IOPORT_RESOURCE</b> function initializes a platform extension plug-in's (PEP) <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a> structure.


## -parameters




### -param Decode [in]

Specifies how to decode the resource address. If bit 0 is a 1, this indicates that the logical device decodes 16-bit addresses. If bit 0 is 0, this indicates that the logical device only decodes the first 10 bits of the address.

Bits 1 to 7 of this parameter are reserved and must be set to zero.


### -param MinimumAddress [in]

Specifies the minimum acceptable starting address for the IO range.


### -param MaximumAddress [in]

Specifies the maximum acceptable starting address for the IO range.


### -param Alignment [in]

Specifies the alignment granularity for the IO address assigned.


### -param PortLength [in]

Specifies the number of bytes in the IO range.


### -param Resource [out]

A pointer to the resource. The structure behind the pointer is of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_io_memory_resource">PEP_ACPI_IO_MEMORY_RESOURCE</a>
 

 

