---
UID: NE:pepfx._PEP_ACPI_OBJECT_TYPE
title: "_PEP_ACPI_OBJECT_TYPE"
author: windows-driver-content
description: The PEP_ACPI_OBJECT_TYPE enumeration indicates the type of ACPI object.
old-location: kernel\pep_acpi_object_type.htm
old-project: kernel
ms.assetid: 81875C20-8E0E-4BAC-B85F-3D275F8B4708
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE, PEP_ACPI_OBJECT_TYPE enumeration [Kernel-Mode Driver Architecture], PepAcpiObjectTypeMaximum, PepAcpiObjectTypeMethod, _PEP_ACPI_OBJECT_TYPE, kernel.pep_acpi_object_type, pepfx/PEP_ACPI_OBJECT_TYPE, pepfx/PepAcpiObjectTypeMaximum, pepfx/PepAcpiObjectTypeMethod"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_OBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_TYPE, *PPEP_ACPI_OBJECT_TYPE
---

# _PEP_ACPI_OBJECT_TYPE enumeration


## -description


The <b>PEP_ACPI_OBJECT_TYPE</b> enumeration indicates the type of ACPI object.


## -syntax


````
typedef enum _PEP_ACPI_OBJECT_TYPE { 
  PepAcpiObjectTypeMethod,
  PepAcpiObjectTypeMaximum
} PEP_ACPI_OBJECT_TYPE;
````


## -enum-fields




### -field PepAcpiObjectTypeMethod

The object is an ACPI control method.


### -field PepAcpiObjectTypeDevice


### -field PepAcpiObjectTypeMaximum

Reserved for use by the operating system.


## -remarks



The <b>Type</b> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is an <b>PEP_ACPI_OBJECT_TYPE</b> enumeration value.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_OBJECT_TYPE enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

