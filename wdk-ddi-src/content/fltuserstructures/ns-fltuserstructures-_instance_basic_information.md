---
UID: NS:fltuserstructures._INSTANCE_BASIC_INFORMATION
title: "_INSTANCE_BASIC_INFORMATION"
author: windows-driver-content
description: The INSTANCE_BASIC_INFORMATION structure contains basic information for a minifilter instance.
old-location: ifsk\instance_basic_information.htm
old-project: ifsk
ms.assetid: 35e2b098-1bc2-4ffc-86c8-b60b651df027
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fltuserstructures/INSTANCE_BASIC_INFORMATION, PINSTANCE_BASIC_INFORMATION structure pointer [Installable File System Drivers], INSTANCE_BASIC_INFORMATION, PINSTANCE_BASIC_INFORMATION, FltSystemStructures_bc615e69-e0f4-478b-9684-9371d62f5602.xml, fltuserstructures/PINSTANCE_BASIC_INFORMATION, INSTANCE_BASIC_INFORMATION structure [Installable File System Drivers], _INSTANCE_BASIC_INFORMATION, ifsk.instance_basic_information
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltuserstructures.h
apiname:
-	INSTANCE_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: PINSTANCE_BASIC_INFORMATION, INSTANCE_BASIC_INFORMATION
---

# _INSTANCE_BASIC_INFORMATION structure


## -description


The INSTANCE_BASIC_INFORMATION structure contains basic information for a minifilter instance. 


## -syntax


````
typedef struct _INSTANCE_BASIC_INFORMATION {
  ULONG  NextEntryOffset;
  USHORT InstanceNameLength;
  USHORT InstanceNameBufferOffset;
} INSTANCE_BASIC_INFORMATION, *PINSTANCE_BASIC_INFORMATION;
````


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

<a href="..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md">INSTANCE_PARTIAL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541535">FilterVolumeInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540538">FilterInstanceFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20INSTANCE_BASIC_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

