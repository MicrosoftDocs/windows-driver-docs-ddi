---
UID: NS:fltuserstructures._FILTER_VOLUME_BASIC_INFORMATION
title: "_FILTER_VOLUME_BASIC_INFORMATION"
author: windows-driver-content
description: The caller-allocated FILTER_VOLUME_BASIC_INFORMATION structure contains basic information for a volume.
old-location: ifsk\filter_volume_basic_information.htm
old-project: ifsk
ms.assetid: f6b5ccc2-81d6-47be-94dd-cf92842de51c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltSystemStructures_7bc0a3dc-37e1-4783-aecd-f4ef96e38a32.xml, PFILTER_VOLUME_BASIC_INFORMATION, _FILTER_VOLUME_BASIC_INFORMATION, PFILTER_VOLUME_BASIC_INFORMATION structure pointer [Installable File System Drivers], fltuserstructures/PFILTER_VOLUME_BASIC_INFORMATION, ifsk.filter_volume_basic_information, FILTER_VOLUME_BASIC_INFORMATION structure [Installable File System Drivers], fltuserstructures/FILTER_VOLUME_BASIC_INFORMATION, *PFILTER_VOLUME_BASIC_INFORMATION, FILTER_VOLUME_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
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
-	FILTER_VOLUME_BASIC_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILTER_VOLUME_BASIC_INFORMATION, FILTER_VOLUME_BASIC_INFORMATION"
---

# _FILTER_VOLUME_BASIC_INFORMATION structure


## -description


The caller-allocated FILTER_VOLUME_BASIC_INFORMATION  structure contains basic information for a volume.


## -syntax


````
typedef struct _FILTER_VOLUME_BASIC_INFORMATION {
  USHORT FilterVolumeNameLength;
  WCHAR  FilterVolumeName[1];
} FILTER_VOLUME_BASIC_INFORMATION, *PFILTER_VOLUME_BASIC_INFORMATION;
````


## -struct-fields




### -field FilterVolumeNameLength

Read-only length, in bytes, of the volume name.


### -field FilterVolumeName

Read-only name of the volume of <b>FilterVolumeNameLength</b> length.  This Unicode string is not NULL-terminated. 


## -remarks



Filter manager enumeration routines, such as <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>, can fill a buffer with structures of type FILTER_VOLUME_BASIC_INFORMATION where each structure represents a volume known to filter manager.  This list of structures can contain multiple volumes with the same name.  For more information, see <a href="https://msdn.microsoft.com/c05982dc-4124-4f9a-93b8-0e56ac296d1b">Understanding Volume Enumerations with Duplicate Volume Names</a>.

The FILTER_VOLUME_BASIC_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each structure falls on an 8-byte boundary.

A FILTER_VOLUME_BASIC_INFORMATION structure can be allocated from paged or nonpaged pool.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541525">FilterVolumeFindFirst</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541530">FilterVolumeFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541522">FilterVolumeFindClose</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_standard_information.md">FILTER_VOLUME_STANDARD_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_VOLUME_BASIC_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

