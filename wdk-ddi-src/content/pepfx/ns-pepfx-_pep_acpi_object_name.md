---
UID: NS:pepfx._PEP_ACPI_OBJECT_NAME
title: "_PEP_ACPI_OBJECT_NAME"
description: The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object.
old-location: kernel\pep_acpi_object_name.htm
tech.root: kernel
ms.assetid: 55D8A977-DA91-4CB5-8549-E1CB1731256C
ms.date: 04/30/2018
ms.keywords: "*PPEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME union [Kernel-Mode Driver Architecture], _PEP_ACPI_OBJECT_NAME, kernel.pep_acpi_object_name, pepfx/PEP_ACPI_OBJECT_NAME"
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
-	PEP_ACPI_OBJECT_NAME
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME
---

# _PEP_ACPI_OBJECT_NAME structure


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



The <i>Name</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186684">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union. Also, the <i>Name</i> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186688">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186684">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186688">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>
 

 

