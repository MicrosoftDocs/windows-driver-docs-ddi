---
UID: NS:fltuserstructures._FILTER_VOLUME_STANDARD_INFORMATION
title: "_FILTER_VOLUME_STANDARD_INFORMATION" (fltuserstructures.h)
description: The caller-allocated FILTER_VOLUME_STANDARD_INFORMATION structure contains information for a volume.
old-location: ifsk\filter_volume_standard_information.htm
tech.root: ifsk
ms.assetid: 51f2f837-7d67-4a9d-a365-d9d1b24977e5
ms.date: 04/16/2018
ms.keywords: "*PFILTER_VOLUME_STANDARD_INFORMATION, FILTER_VOLUME_STANDARD_INFORMATION, FILTER_VOLUME_STANDARD_INFORMATION structure [Installable File System Drivers], FltSystemStructures_cf6b475f-0334-4d11-8449-f66c611011bf.xml, PFILTER_VOLUME_STANDARD_INFORMATION, PFILTER_VOLUME_STANDARD_INFORMATION structure pointer [Installable File System Drivers], _FILTER_VOLUME_STANDARD_INFORMATION, fltuserstructures/FILTER_VOLUME_STANDARD_INFORMATION, fltuserstructures/PFILTER_VOLUME_STANDARD_INFORMATION, ifsk.filter_volume_standard_information"
ms.topic: struct
req.header: fltuserstructures.h
req.include-header: FltUser.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
-	fltuserstructures.h
api_name:
-	FILTER_VOLUME_STANDARD_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILTER_VOLUME_STANDARD_INFORMATION, *PFILTER_VOLUME_STANDARD_INFORMATION
---

# _FILTER_VOLUME_STANDARD_INFORMATION structure


## -description


The  caller-allocated FILTER_VOLUME_STANDARD_INFORMATION structure contains information for a volume.


## -struct-fields




### -field NextEntryOffset

Read-only offset, in bytes, of the next FILTER_VOLUME_STANDARD_INFORMATION structure if multiple structures are present in the buffer. This member is zero if no other structures follow this one.


### -field Flags

A read-only bitmask of system-defined flags that describe attributes of the volume. The following are valid flag values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_VSI_DETACHED_VOLUME

</td>
<td>
The volume in not currently attached to a storage stack.

</td>
</tr>
</table>
 


### -field FrameID

Read-only member used to identify the filter manager frame that the volume is in.


### -field FileSystemType

Read-only member used to identify the type of file system being used on the volume.  The possible values for this member are listed in <a href="https://msdn.microsoft.com/library/windows/hardware/ff625876">FLT_FILESYSTEM_TYPE</a>.


### -field FilterVolumeNameLength

Read-only length, in bytes, of the volume name.


### -field FilterVolumeName

Read-only name of the volume of <b>FilterVolumeNameLength</b> length.  This Unicode string is not NULL-terminated.


## -remarks



Filter manager enumeration routines, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>, can fill a buffer with structures of type FILTER_VOLUME_STANDARD_INFORMATION where each structure represents a volume known to filter manager.  This list of structures  can contain multiple volumes with the same name.  For more information, see <a href="https://msdn.microsoft.com/c05982dc-4124-4f9a-93b8-0e56ac296d1b">Understanding Volume Enumerations with Duplicate Volume Names</a>.

The FILTER_VOLUME_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry falls on an 8-byte boundary.

A FILTER_VOLUME_STANDARD_INFORMATION structure can be allocated from paged or nonpaged pool.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541631">FILTER_VOLUME_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541522">FilterVolumeFindClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541525">FilterVolumeFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541530">FilterVolumeFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542091">FltEnumerateVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542092">FltEnumerateVolumes</a>
 

 

