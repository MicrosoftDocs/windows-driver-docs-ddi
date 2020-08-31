---
UID: NS:pepfx._PEP_ACPI_RESOURCE_FLAGS
title: _PEP_ACPI_RESOURCE_FLAGS (pepfx.h)
description: The PEP_ACPI_RESOURCE_FLAGS structure contains flags describing an ACPI resource.
old-location: kernel\pep_acpi_resource_flags.htm
tech.root: kernel
ms.assetid: 1BB4933B-2707-4350-8D9C-E0E25A85F5CB
ms.date: 04/30/2018
keywords: ["PEP_ACPI_RESOURCE_FLAGS structure"]
ms.keywords: "*PPEP_ACPI_RESOURCE_FLAGS, PEP_ACPI_RESOURCE_FLAGS, PEP_ACPI_RESOURCE_FLAGS union [Kernel-Mode Driver Architecture], PPEP_ACPI_RESOURCE_FLAGS, PPEP_ACPI_RESOURCE_FLAGS union pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_RESOURCE_FLAGS, kernel.pep_acpi_resource_flags, pepfx/PEP_ACPI_RESOURCE_FLAGS, pepfx/PPEP_ACPI_RESOURCE_FLAGS"
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
targetos: Windows
req.typenames: PEP_ACPI_RESOURCE_FLAGS, *PPEP_ACPI_RESOURCE_FLAGS
f1_keywords:
 - _PEP_ACPI_RESOURCE_FLAGS
 - pepfx/_PEP_ACPI_RESOURCE_FLAGS
 - PPEP_ACPI_RESOURCE_FLAGS
 - pepfx/PPEP_ACPI_RESOURCE_FLAGS
 - PEP_ACPI_RESOURCE_FLAGS
 - pepfx/PEP_ACPI_RESOURCE_FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_RESOURCE_FLAGS
---

# _PEP_ACPI_RESOURCE_FLAGS structure


## -description

> [!NOTE]
> Microsoft supports a diverse and inclusionary environment.  Within this document, there are references to the word slave. Microsoft's [Style Guide for Bias-Free Communications](https://docs.microsoft.com/style-guide/bias-free-communication) recognizes this as an exclusionary word.  This wording is used as it is currently the wording used within the software. When this word is removed from the software, we will correct this document to be in alignment.


The <b>PEP_ACPI_RESOURCE_FLAGS</b> structure contains flags describing an ACPI resource.

## -struct-fields

### -field AsULong

The consolidated values of the flags in <b>DUMMYSTRUCTNAME</b>.

### -field DUMMYSTRUCTNAME

 A structure containing ACPI resource flags.

### -field DUMMYSTRUCTNAME.Shared

When set, indicates that this is a shared device.

### -field DUMMYSTRUCTNAME.Wake

When set, indicates that this device can be woken from a low-power state.

### -field DUMMYSTRUCTNAME.ResourceUsage

When set, indicates that this device is in use.

### -field DUMMYSTRUCTNAME.SlaveMode

When set, indicates that this device is in slave mode.

### -field DUMMYSTRUCTNAME.AddressingMode

When set, indicates that this device is in addressing mode.

### -field DUMMYSTRUCTNAME.SharedMode

When set, indicates that this device is in shared mode.

### -field DUMMYSTRUCTNAME.Reserved

This member is reserved and should be set to zero.

