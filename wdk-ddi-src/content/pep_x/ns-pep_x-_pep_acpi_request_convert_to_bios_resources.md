---
UID: NS:pep_x._PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
title: _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES (pep_x.h)
description: The PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure is used in the process of converting ACPI resources to BIOS resources by one of the PEP initialization functions.
old-location: kernel\pep_acpi_request_convert_to_bios_resources.htm
tech.root: kernel
ms.assetid: DF9FD748-88E8-4E32-B698-0E8A3BE319DB
ms.date: 04/30/2018
keywords: ["PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure"]
ms.keywords: "*PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure [Kernel-Mode Driver Architecture], PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, kernel.pep_acpi_request_convert_to_bios_resources, pepfx/PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, pepfx/PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES"
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
req.typenames: PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES, *PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
f1_keywords:
 - _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
 - pep_x/_PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
 - PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
 - pep_x/PPEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
 - PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
 - pep_x/PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES
---

# _PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES structure


## -description

The <b>PEP_ACPI_REQUEST_CONVERT_TO_BIOS_RESOURCES</b> structure is used in the process of converting ACPI resources to BIOS resources by one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP initialization functions</a>.

## -struct-fields

### -field TranslationStatus

The result code from the resource translation call.

### -field InputBuffer

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource">PEP_ACPI_RESOURCE</a> containing the input buffer.

### -field InputBufferSize

The size of the input buffer.

### -field OutputBuffer

A pointer to the output buffer containing the translated structure.

### -field OutputBufferSize

The size of the output buffer.

### -field Flags

The value contained in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">PEP initialization functions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource">PEP_ACPI_RESOURCE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_resource_flags">PEP_ACPI_RESOURCE_FLAGS</a>

