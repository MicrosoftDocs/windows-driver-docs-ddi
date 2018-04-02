---
UID: NS:fltuserstructures._INSTANCE_BASIC_INFORMATION
title: "_INSTANCE_BASIC_INFORMATION"
author: windows-driver-content
description: The INSTANCE_BASIC_INFORMATION structure contains basic information for a minifilter instance.
old-location: ifsk\instance_basic_information.htm
old-project: ifsk
ms.assetid: 35e2b098-1bc2-4ffc-86c8-b60b651df027
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltSystemStructures_bc615e69-e0f4-478b-9684-9371d62f5602.xml, INSTANCE_BASIC_INFORMATION, INSTANCE_BASIC_INFORMATION structure [Installable File System Drivers], PINSTANCE_BASIC_INFORMATION, PINSTANCE_BASIC_INFORMATION structure pointer [Installable File System Drivers], _INSTANCE_BASIC_INFORMATION, fltuserstructures/INSTANCE_BASIC_INFORMATION, fltuserstructures/PINSTANCE_BASIC_INFORMATION, ifsk.instance_basic_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	INSTANCE_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: INSTANCE_BASIC_INFORMATION, PINSTANCE_BASIC_INFORMATION
---

# _INSTANCE_BASIC_INFORMATION structure


## -description


The INSTANCE_BASIC_INFORMATION structure contains basic information for a minifilter instance. 


## -struct-fields




### -field NextEntryOffset

Byte offset of the next INSTANCE_BASIC_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


### -field InstanceNameLength

Length, in bytes, of the instance name. 


### -field InstanceNameBufferOffset

Byte offset of the first character of the instance name string. This character is followed in memory by the remainder of the string. 


## -remarks



This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540538">FilterInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541535">FilterVolumeInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548172">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548185">INSTANCE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548190">INSTANCE_PARTIAL_INFORMATION</a>
 

 

