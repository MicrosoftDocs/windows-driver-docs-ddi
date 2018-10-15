---
UID: NS:pep_x._PEP_ACPI_QUERY_OBJECT_INFORMATION
title: "_PEP_ACPI_QUERY_OBJECT_INFORMATION"
author: windows-driver-content
description: The PEP_ACPI_QUERY_OBJECT_INFORMATION structure contains information about an ACPI object.
old-location: kernel\pep_acpi_query_object_information.htm
tech.root: kernel
ms.assetid: 71E43364-CBD6-4628-B51C-B41315E0E800
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_ACPI_QUERY_OBJECT_INFORMATION, PEP_ACPI_QUERY_OBJECT_INFORMATION, PEP_ACPI_QUERY_OBJECT_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_ACPI_QUERY_OBJECT_INFORMATION, PPEP_ACPI_QUERY_OBJECT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_ACPI_QUERY_OBJECT_INFORMATION, kernel.pep_acpi_query_object_information, pepfx/PEP_ACPI_QUERY_OBJECT_INFORMATION, pepfx/PPEP_ACPI_QUERY_OBJECT_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_ACPI_QUERY_OBJECT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PEP_ACPI_QUERY_OBJECT_INFORMATION, *PPEP_ACPI_QUERY_OBJECT_INFORMATION
---

# _PEP_ACPI_QUERY_OBJECT_INFORMATION structure


## -description


The <b>PEP_ACPI_QUERY_OBJECT_INFORMATION</b> structure contains information about an ACPI object.


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device's registration for ACPI services. The platform extension plug-in (PEP) supplied this handle in response to a previous <a href="https://msdn.microsoft.com/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a> notification.


### -field Name

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/mt629110">PEP_ACPI_OBJECT_NAME</a> union that specifies the path-relative, four-character name of the object.


### -field Type

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186685">PEP_ACPI_OBJECT_TYPE</a> enumeration value that specifies the object type. Currently, a control method is the only object type that is defined for this member (<b>Type</b> = <b>PepAcpiObjectTypeMethod</b>).


### -field ObjectFlags

[in] A set of input flags. No flags are currently defined for this member, which is always set to PEP_ACPI_OBJECT_FLAG_NONE (0x0).


### -field DUMMYUNIONNAME

The query result. If the specified object is a control method, the platform extension plug-in (PEP) writes the query result to the <b>MethodObject</b> member of this union.


### -field DUMMYUNIONNAME.MethodObject

[out] Information about a control method object.


### -field DUMMYUNIONNAME.MethodObject.InputArgumentCount

The number of input arguments expected by the control method.


### -field DUMMYUNIONNAME.MethodObject.OutputArgumentCount

The number of output arguments produced by the control method.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt629114">PEP_NOTIFY_ACPI_QUERY_OBJECT_INFORMATION</a> notification. The <b>Name</b>, <b>Type</b>, and <b>Flags</b> members of the structure contain input values that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies when this notification is sent. The <b>MethodObject</b> member contains an output value that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt629110">PEP_ACPI_OBJECT_NAME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186685">PEP_ACPI_OBJECT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629114">PEP_NOTIFY_ACPI_QUERY_OBJECT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186689">PEP_NOTIFY_ACPI_REGISTER_DEVICE</a>
 

 

