---
UID: NS:acpiioct._ACPI_ENUM_CHILDREN_INPUT_BUFFER
title: "_ACPI_ENUM_CHILDREN_INPUT_BUFFER"
author: windows-driver-content
description: The ACPI_ENUM_CHILDREN_INPUT_BUFFER structure is used as input to an IOCTL_ACPI_ENUM_CHILDREN request. The structure specifies which child objects to enumerate in the namespace of the device to which the request is sent.
old-location: acpi\acpi_enum_children_input_buffer.htm
old-project: acpi
ms.assetid: fba604bc-2fab-448c-bbc7-8ea30ff6de6b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PACPI_ENUM_CHILDREN_INPUT_BUFFER, ,, A, ACPI_ENUM_CHILDREN_INPUT_BUFFER, ACPI_ENUM_CHILDREN_INPUT_BUFFER structure [ACPI Devices], B, C, D, E, F, H, I, L, M, N, P, PACPI_ENUM_CHILDREN_INPUT_BUFFER, PACPI_ENUM_CHILDREN_INPUT_BUFFER structure pointer [ACPI Devices], R, T, U, _, _ACPI_ENUM_CHILDREN_INPUT_BUFFER, acpi-meth-eval-ref_3d8ce8a3-94f9-4ea0-9a16-f76c08928fc4.xml, acpi.acpi_enum_children_input_buffer, acpiioct/ACPI_ENUM_CHILDREN_INPUT_BUFFER, acpiioct/PACPI_ENUM_CHILDREN_INPUT_BUFFER"
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
-	ACPI_ENUM_CHILDREN_INPUT_BUFFER
product: Windows
targetos: Windows
req.typenames: ACPI_ENUM_CHILDREN_INPUT_BUFFER, *PACPI_ENUM_CHILDREN_INPUT_BUFFER
---

# _ACPI_ENUM_CHILDREN_INPUT_BUFFER structure


## -description


The ACPI_ENUM_CHILDREN_INPUT_BUFFER structure is used as input to an <a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a> request. The structure specifies which child objects to enumerate in the namespace of the device to which the request is sent. 


## -syntax


````
typedef struct _ACPI_ENUM_CHILDREN_INPUT_BUFFER {
  ULONG Signature;
  ULONG Flags;
  ULONG NameLength;
  CHAR  Name[ANYSIZE_ARRAY];
} ACPI_ENUM_CHILDREN_INPUT_BUFFER, *PACPI_ENUM_CHILDREN_INPUT_BUFFER;
````


## -struct-fields




### -field Signature

The signature of the input buffer, which must be set to ACPI_ENUM_CHILDREN_INPUT_BUFFER_SIGNATURE.


### -field Flags

A flag that determines which objects the ACPI driver enumerates, as described in the Remarks section later in this topic.


### -field NameLength

The number of ASCII characters, including a NULL-terminator, that the <b>Name</b> array contains.


### -field Name

A NULL-terminated, four-character ASCII string that contains the name of a child object that the ACPI driver uses to restrict the enumeration to child objects of the same name. For more information about how to supply an object name, see the Remarks section later in this topic.


## -remarks




<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a> supports the following types of enumerations, depending on how the <b>Flags</b> member is set in the corresponding ACPI_ENUM_CHILDREN_INPUT_BUFFER structure:



For information about how to enumerate child objects of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.




## -see-also

<a href="..\acpiioct\ni-acpiioct-ioctl_acpi_enum_children.md">IOCTL_ACPI_ENUM_CHILDREN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20ACPI_ENUM_CHILDREN_INPUT_BUFFER structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

