---
UID: NS:pepfx._PEP_ACPI_OBJECT_NAME
title: _PEP_ACPI_OBJECT_NAME (pepfx.h)
description: The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object.
old-location: kernel\pep_acpi_object_name.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_ACPI_OBJECT_NAME structure"]
ms.keywords: "*PPEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME union [Kernel-Mode Driver Architecture], _PEP_ACPI_OBJECT_NAME, kernel.pep_acpi_object_name, pepfx/PEP_ACPI_OBJECT_NAME"
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
req.typenames: PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME
f1_keywords:
 - _PEP_ACPI_OBJECT_NAME
 - pepfx/_PEP_ACPI_OBJECT_NAME
 - PPEP_ACPI_OBJECT_NAME
 - pepfx/PPEP_ACPI_OBJECT_NAME
 - PEP_ACPI_OBJECT_NAME
 - pepfx/PEP_ACPI_OBJECT_NAME
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_ACPI_OBJECT_NAME
---

# _PEP_ACPI_OBJECT_NAME structure (pepfx.h)


## -description

The <b>PEP_ACPI_OBJECT_NAME</b> union contains the four-character name of an ACPI object.

## -struct-fields

### -field Name

### -field NameAsUlong

 




#### - ObjectName

The object name stored as an array of four 8-bit unsigned characters.


#### - ObjectNameAsUlong

The object name stored as a single 32-bit unsigned integer value.

## -remarks

The <i>Name</i> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_object_name_with_type">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union. Also, the <i>Name</i> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_query_object_information">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_object_name_with_type">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_query_object_information">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>
