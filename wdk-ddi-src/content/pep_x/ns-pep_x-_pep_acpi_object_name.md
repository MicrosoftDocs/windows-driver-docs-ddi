---
UID: NS:pep_x._PEP_ACPI_OBJECT_NAME
title: _PEP_ACPI_OBJECT_NAME (pep_x.h)
description: Learn how the PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object.
old-location: kernel\pep_acpi_object_name.htm
tech.root: kernel
ms.date: 08/05/2022
keywords: ["PEP_ACPI_OBJECT_NAME structure"]
ms.keywords: "*PPEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME union [Kernel-Mode Driver Architecture], _PEP_ACPI_OBJECT_NAME, kernel.pep_acpi_object_name, pepfx/PEP_ACPI_OBJECT_NAME"
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
req.typenames: PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME
f1_keywords:
 - _PEP_ACPI_OBJECT_NAME
 - pep_x/_PEP_ACPI_OBJECT_NAME
 - PPEP_ACPI_OBJECT_NAME
 - pep_x/PPEP_ACPI_OBJECT_NAME
 - PEP_ACPI_OBJECT_NAME
 - pep_x/PEP_ACPI_OBJECT_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_ACPI_OBJECT_NAME
 - PPEP_ACPI_OBJECT_NAME
 - PEP_ACPI_OBJECT_NAME
---

# _PEP_ACPI_OBJECT_NAME structure (pep_x.h)

## -description

The **PEP_ACPI_OBJECT_NAME** union contains the four-character name of an ACPI object.

## -struct-fields

### -field Name

The object name stored as an array of four 8-bit unsigned characters.

### -field NameAsUlong

The object name stored as a single 32-bit unsigned integer value.

## -remarks

The *Name* member of the [PEP_ACPI_OBJECT_NAME_WITH_TYPE](../pepfx/ns-pepfx-_pep_acpi_object_name_with_type.md) structure is a **PEP_ACPI_OBJECT_NAME** union. Also, the *Name* member of the [PEP_ACPI_QUERY_OBJECT_INFORMATION](../pepfx/ns-pepfx-_pep_acpi_query_object_information.md) structure is a **PEP_ACPI_OBJECT_NAME** union.

## -see-also

- [PEP_ACPI_OBJECT_NAME_WITH_TYPE](../pepfx/ns-pepfx-_pep_acpi_object_name_with_type.md)
- [PEP_ACPI_QUERY_OBJECT_INFORMATION](../pepfx/ns-pepfx-_pep_acpi_query_object_information.md)
