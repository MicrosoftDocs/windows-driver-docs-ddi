---
UID: NS:acpiioct._ACPI_ENUM_CHILD
title: "_ACPI_ENUM_CHILD"
author: windows-driver-content
description: The ACPI_ENUM_CHILD structure is a member of the ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure and contains the full path and name of an object in an ACPI namespace.
old-location: acpi\acpi_enum_child.htm
old-project: acpi
ms.assetid: baa0292a-b327-4fc0-9235-b1b977f93bf9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ACPI_ENUM_CHILD structure [ACPI Devices], acpi-meth-eval-ref_7ffcb8d5-da55-4ed9-88db-8f954d01852b.xml, acpiioct/ACPI_ENUM_CHILD, _ACPI_ENUM_CHILD, acpi.acpi_enum_child, *PACPI_ENUM_CHILD, ACPI_ENUM_CHILD
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Acpiioct.h
apiname:
-	ACPI_ENUM_CHILD
product: Windows
targetos: Windows
req.typenames: ACPI_ENUM_CHILD
---

# _ACPI_ENUM_CHILD structure


## -description


The ACPI_ENUM_CHILD structure is a member of the <a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_output_buffer.md">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure and contains the full path and name of an object in an ACPI namespace.


## -syntax


````
typedef struct _ACPI_ENUM_CHILD {
  ULONG Flags;
  ULONG NameLength;
  CHAR  Name[ANYSIZE_ARRAY];
} ACPI_ENUM_CHILD;
````


## -struct-fields




### -field Flags

A flag value that the ACPI driver sets to ACPI_OBJECT_HAS_CHILDREN if the enumerated child object has child objects; otherwise, the ACPI driver does not set this value.


### -field NameLength

The number of characters, including a NULL-terminated character, in the ASCII string that the <b>Name</b> array contains.


### -field Name

A NULL-terminated ASCII string that contains the path and name of an object in an ACPI namespace. For more information about the format of the path and name, see the Remarks section later in this topic.


## -remarks



A driver for a device uses an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a> request to enumerate the child objects of the device. The enumerated child objects can be devices or any object of a supplied name. This request returns an ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure, which includes the <b>Children</b> member that contains an array of ACPI_ENUM_CHILD structures. 

The path and name that are contained in a <b>Name</b> member are in the standard format for a fully qualified path and name of an object in an ACPI namespace. For example, assume that a device named 'ABCD' is an immediate child of the root of an ACPI namespace, that device 'ABCD' has a child device named 'CHLD,' and that child device 'CHLD' has an immediate child object named '_FOO.' In this case, <b>Name</b> would contain '\ABCD.CHLD._FOO.'

For information about how to enumerate child objects of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.




## -see-also

<a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_output_buffer.md">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_ENUM_CHILD structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

