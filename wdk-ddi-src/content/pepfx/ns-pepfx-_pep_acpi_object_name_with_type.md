---
UID: NS:pepfx._PEP_ACPI_OBJECT_NAME_WITH_TYPE
title: _PEP_ACPI_OBJECT_NAME_WITH_TYPE (pepfx.h)
description: The PEP_ACPI_OBJECT_NAME_WITH_TYPE structure that specifies both the path-relative name of an ACPI object and the type of this object.
old-location: kernel\pep_acpi_object_name_with_type.htm
tech.root: kernel
ms.assetid: 7DD01461-4890-4095-A55C-771EA0EEA642
ms.date: 04/30/2018
ms.keywords: "*PPEP_ACPI_OBJECT_NAME_WITH_TYPE, PEP_ACPI_OBJECT_NAME_WITH_TYPE, PEP_ACPI_OBJECT_NAME_WITH_TYPE structure [Kernel-Mode Driver Architecture], PPEP_ACPI_OBJECT_NAME_WITH_TYPE, PPEP_ACPI_OBJECT_NAME_WITH_TYPE structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_OBJECT_NAME_WITH_TYPE, kernel.pep_acpi_object_name_with_type, pepfx/PEP_ACPI_OBJECT_NAME_WITH_TYPE, pepfx/PPEP_ACPI_OBJECT_NAME_WITH_TYPE"
ms.topic: struct
f1_keywords:
 - "pepfx/PEP_ACPI_OBJECT_NAME_WITH_TYPE"
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
- PEP_ACPI_OBJECT_NAME_WITH_TYPE
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_NAME_WITH_TYPE, *PPEP_ACPI_OBJECT_NAME_WITH_TYPE
---

# _PEP_ACPI_OBJECT_NAME_WITH_TYPE structure


## -description


The <b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b> structure that specifies both the path-relative name of an ACPI object and the type of this object.


## -struct-fields




### -field Name

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_acpi_object_name">PEP_ACPI_OBJECT_NAME</a> structure that contains the four-character name of the ACPI object.


### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_acpi_object_type">PEP_ACPI_OBJECT_TYPE</a> enumeration value that indicates the type of ACPI object. Currently, the only supported object type is a control method.


## -remarks



The <b>Objects</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_acpi_enumerate_device_namespace">PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</a> structure is the first element in an array of <b>PEP_ACPI_OBJECT_NAME_WITH_TYPE</b> structures.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_acpi_enumerate_device_namespace">PEP_ACPI_ENUMERATE_DEVICE_NAMESPACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_acpi_object_name">PEP_ACPI_OBJECT_NAME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ne-pepfx-_pep_acpi_object_type">PEP_ACPI_OBJECT_TYPE</a>
 

 

