---
UID: NS:pepfx._PEP_ACPI_OBJECT_NAME
title: "_PEP_ACPI_OBJECT_NAME"
author: windows-driver-content
description: The PEP_ACPI_OBJECT_NAME union contains the four-character name of an ACPI object.
old-location: kernel\pep_acpi_object_name.htm
old-project: kernel
ms.assetid: 55D8A977-DA91-4CB5-8549-E1CB1731256C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPEP_ACPI_OBJECT_NAME, ,, A, B, C, E, I, J, M, N, O, P, PEP_ACPI_OBJECT_NAME, PEP_ACPI_OBJECT_NAME union [Kernel-Mode Driver Architecture], T, _, _PEP_ACPI_OBJECT_NAME, kernel.pep_acpi_object_name, pepfx/PEP_ACPI_OBJECT_NAME"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_ACPI_OBJECT_NAME
product: Windows
targetos: Windows
req.typenames: PEP_ACPI_OBJECT_NAME, *PPEP_ACPI_OBJECT_NAME
---

# _PEP_ACPI_OBJECT_NAME structure


## -description


The <b>PEP_ACPI_OBJECT_NAME</b> union contains the four-character name of an ACPI object.


## -syntax


````
typedef union _PEP_ACPI_OBJECT_NAME {
  UCHAR ObjectName[4];
  ULONG ObjectNameAsUlong;
} PEP_ACPI_OBJECT_NAME;
````


## -struct-fields




### -field Name

 


### -field NameAsUlong

 




#### - ObjectName

The object name stored as an array of four 8-bit unsigned characters.


#### - ObjectNameAsUlong

The object name stored as a single 32-bit unsigned integer value.


## -remarks



The <i>Name</i> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union. Also, the <i>Name</i> member of the <a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a> structure is a <b>PEP_ACPI_OBJECT_NAME</b> union.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_acpi_object_name_with_type.md">PEP_ACPI_OBJECT_NAME_WITH_TYPE</a>



<a href="..\pepfx\ns-pepfx-_pep_acpi_query_object_information.md">PEP_ACPI_QUERY_OBJECT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_ACPI_OBJECT_NAME union%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

