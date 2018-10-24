---
UID: NS:acpiioct._ACPI_ENUM_CHILD
title: "_ACPI_ENUM_CHILD"
author: windows-driver-content
description: The ACPI_ENUM_CHILD structure is a member of the ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure and contains the full path and name of an object in an ACPI namespace.
old-location: acpi\acpi_enum_child.htm
tech.root: acpi
ms.assetid: baa0292a-b327-4fc0-9235-b1b977f93bf9
ms.date: 02/15/2018
ms.keywords: "*PACPI_ENUM_CHILD, ACPI_ENUM_CHILD, ACPI_ENUM_CHILD structure [ACPI Devices], _ACPI_ENUM_CHILD, acpi-meth-eval-ref_7ffcb8d5-da55-4ed9-88db-8f954d01852b.xml, acpi.acpi_enum_child, acpiioct/ACPI_ENUM_CHILD"
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
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
-	Acpiioct.h
api_name:
-	ACPI_ENUM_CHILD
product:
- Windows
targetos: Windows
req.typenames: ACPI_ENUM_CHILD
---

# _ACPI_ENUM_CHILD structure


## -description


The ACPI_ENUM_CHILD structure is a member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure and contains the full path and name of an object in an ACPI namespace.


## -struct-fields




### -field Flags

A flag value that the ACPI driver sets to ACPI_OBJECT_HAS_CHILDREN if the enumerated child object has child objects; otherwise, the ACPI driver does not set this value.


### -field NameLength

The number of characters, including a NULL-terminated character, in the ASCII string that the <b>Name</b> array contains.


### -field Name

A NULL-terminated ASCII string that contains the path and name of an object in an ACPI namespace. For more information about the format of the path and name, see the Remarks section later in this topic.


## -remarks



A driver for a device uses an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536147">IOCTL_ACPI_ENUM_CHILDREN</a> request to enumerate the child objects of the device. The enumerated child objects can be devices or any object of a supplied name. This request returns an ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure, which includes the <b>Children</b> member that contains an array of ACPI_ENUM_CHILD structures. 

The path and name that are contained in a <b>Name</b> member are in the standard format for a fully qualified path and name of an object in an ACPI namespace. For example, assume that a device named 'ABCD' is an immediate child of the root of an ACPI namespace, that device 'ABCD' has a child device named 'CHLD,' and that child device 'CHLD' has an immediate child object named '_FOO.' In this case, <b>Name</b> would contain '\ABCD.CHLD._FOO.'

For information about how to enumerate child objects of a device, see <a href="https://msdn.microsoft.com/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536112">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536147">IOCTL_ACPI_ENUM_CHILDREN</a>
 

 

