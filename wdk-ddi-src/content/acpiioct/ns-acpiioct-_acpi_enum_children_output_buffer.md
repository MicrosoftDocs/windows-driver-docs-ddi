---
UID: NS:acpiioct._ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
title: "_ACPI_ENUM_CHILDREN_OUTPUT_BUFFER"
author: windows-driver-content
description: The ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure contains an array of object names in an ACPI namespace.
old-location: acpi\acpi_enum_children_output_buffer.htm
old-project: acpi
ms.assetid: e7e9fdae-4951-4878-a5b6-81d681eca472
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PACPI_ENUM_CHILDREN_OUTPUT_BUFFER, ACPI_ENUM_CHILDREN_OUTPUT_BUFFER, ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure [ACPI Devices], _ACPI_ENUM_CHILDREN_OUTPUT_BUFFER, acpi-meth-eval-ref_cb8acde5-31cb-4b32-9337-e196db32de8b.xml, acpi.acpi_enum_children_output_buffer, acpiioct/ACPI_ENUM_CHILDREN_OUTPUT_BUFFER"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Acpiioct.h
api_name:
-	ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
product:
- Windows
targetos: Windows
req.typenames: ACPI_ENUM_CHILDREN_OUTPUT_BUFFER
---

# _ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure


## -description


The ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure contains an array of object names in an ACPI namespace. 


## -struct-fields




### -field Signature

The signature of the output buffer, which must be set to ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE.


### -field NumberOfChildren

The number of elements of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> in the <b>Children</b> array.


### -field Children

An array of elements of type ACPI_ENUM_CHILD. Each ACPI_ENUM_CHILD structure contains the path and name of an object in the ACPI namespace.


## -remarks



A driver for a device uses an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536147">IOCTL_ACPI_ENUM_CHILDREN</a> request to enumerate the child objects of the device. The enumerated child objects can be devices or any object of a supplied name. This request returns an ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure, which includes the <b>Children</b> member that contains an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a> structures. 

For information about how to enumerate child objects of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536109">ACPI_ENUM_CHILD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536147">IOCTL_ACPI_ENUM_CHILDREN</a>
 

 

