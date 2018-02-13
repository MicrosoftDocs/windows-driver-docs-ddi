---
UID: NS:acpiioct._ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
title: "_ACPI_ENUM_CHILDREN_OUTPUT_BUFFER"
author: windows-driver-content
description: The ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure contains an array of object names in an ACPI namespace.
old-location: acpi\acpi_enum_children_output_buffer.htm
old-project: acpi
ms.assetid: e7e9fdae-4951-4878-a5b6-81d681eca472
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: "_ACPI_ENUM_CHILDREN_OUTPUT_BUFFER, ACPI_ENUM_CHILDREN_OUTPUT_BUFFER, ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure [ACPI Devices], acpi-meth-eval-ref_cb8acde5-31cb-4b32-9337-e196db32de8b.xml, acpiioct/ACPI_ENUM_CHILDREN_OUTPUT_BUFFER, *PACPI_ENUM_CHILDREN_OUTPUT_BUFFER, acpi.acpi_enum_children_output_buffer"
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
-	ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
product: Windows
targetos: Windows
req.typenames: ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
---

# _ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure


## -description


The ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure contains an array of object names in an ACPI namespace. 


## -syntax


````
typedef struct _ACPI_ENUM_CHILDREN_OUTPUT_BUFFER {
  ULONG           Signature;
  ULONG           NumberOfChildren;
  ACPI_ENUM_CHILD Children[ANYSIZE_ARRAY];
} ACPI_ENUM_CHILDREN_OUTPUT_BUFFER;
````


## -struct-fields




### -field Signature

The signature of the output buffer, which must be set to ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE.


### -field NumberOfChildren

The number of elements of type <a href="..\acpiioct\ns-acpiioct-_acpi_enum_child.md">ACPI_ENUM_CHILD</a> in the <b>Children</b> array.


### -field Children

An array of elements of type ACPI_ENUM_CHILD. Each ACPI_ENUM_CHILD structure contains the path and name of an object in the ACPI namespace.


## -remarks



A driver for a device uses an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a> request to enumerate the child objects of the device. The enumerated child objects can be devices or any object of a supplied name. This request returns an ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure, which includes the <b>Children</b> member that contains an array of <a href="..\acpiioct\ns-acpiioct-_acpi_enum_child.md">ACPI_ENUM_CHILD</a> structures. 

For information about how to enumerate child objects of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.




## -see-also

<a href="..\acpiioct\ns-acpiioct-_acpi_enum_child.md">ACPI_ENUM_CHILD</a>



<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure%20 RELEASE:%20(12/31/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

