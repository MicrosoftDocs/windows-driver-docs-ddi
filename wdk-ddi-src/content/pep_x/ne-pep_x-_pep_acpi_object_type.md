---
UID: NE:pep_x._PEP_ACPI_OBJECT_TYPE
title: _PEP_ACPI_OBJECT_TYPE (pep_x.h)
description: The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object.
old-location: kernel\pep_acpi_object_type.htm
tech.root: kernel
ms.assetid: 81875C20-8E0E-4BAC-B85F-3D275F8B4708
ms.date: 04/30/2018
keywords: ["PEP_ACPI_OBJECT_TYPE enumeration"]
ms.keywords: "*PPEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE enumeration [Kernel-Mode Driver Architecture], PepAcpiObjectTypeMaximum, PepAcpiObjectTypeMethod, _PEP_ACPI_OBJECT_TYPE, kernel.pep_acpi_object_type, pepfx/PEP_ACPI_OBJECT_TYPE, pepfx/PepAcpiObjectTypeMaximum, pepfx/PepAcpiObjectTypeMethod"
f1_keywords:
 - "pep_x/PEP_ACPI_OBJECT_TYPE"
 - "PEP_ACPI_OBJECT_TYPE"
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
- PEP_ACPI_OBJECT_TYPE
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_TYPE, *PPEP_ACPI_OBJECT_TYPE
---

# _PEP_ACPI_OBJECT_TYPE enumeration


## -description


The <b>PEP_ACPI_OBJECT_TYPE</b> enumeration indicates the type of ACPI object.


## -enum-fields




### -field PepAcpiObjectTypeMethod

The object is an ACPI control method.


### -field PepAcpiObjectTypeDevice


### -field PepAcpiObjectTypeMaximum

Reserved for use by the operating system.


## -remarks



The <b>Type</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_query_object_information">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is an <b>PEP_ACPI_OBJECT_TYPE</b> enumeration value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_acpi_query_object_information">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>
 

 

