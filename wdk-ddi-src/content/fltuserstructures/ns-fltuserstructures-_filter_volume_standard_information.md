---
UID: NS:fltuserstructures._FILTER_VOLUME_STANDARD_INFORMATION
title: "_FILTER_VOLUME_STANDARD_INFORMATION"
author: windows-driver-content
description: The caller-allocated FILTER_VOLUME_STANDARD_INFORMATION structure contains information for a volume.
old-location: ifsk\filter_volume_standard_information.htm
old-project: ifsk
ms.assetid: 51f2f837-7d67-4a9d-a365-d9d1b24977e5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILTER_VOLUME_STANDARD_INFORMATION, FILTER_VOLUME_STANDARD_INFORMATION, FILTER_VOLUME_STANDARD_INFORMATION structure [Installable File System Drivers], FltSystemStructures_cf6b475f-0334-4d11-8449-f66c611011bf.xml, PFILTER_VOLUME_STANDARD_INFORMATION, PFILTER_VOLUME_STANDARD_INFORMATION structure pointer [Installable File System Drivers], _FILTER_VOLUME_STANDARD_INFORMATION, fltuserstructures/FILTER_VOLUME_STANDARD_INFORMATION, fltuserstructures/PFILTER_VOLUME_STANDARD_INFORMATION, ifsk.filter_volume_standard_information"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltuserstructures.h
api_name:
-	FILTER_VOLUME_STANDARD_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILTER_VOLUME_STANDARD_INFORMATION, *PFILTER_VOLUME_STANDARD_INFORMATION
---

# _FILTER_VOLUME_STANDARD_INFORMATION structure


## -description


The  caller-allocated FILTER_VOLUME_STANDARD_INFORMATION structure contains information for a volume.


## -syntax


````
typedef struct _FILTER_VOLUME_STANDARD_INFORMATION {
  ULONG               NextEntryOffset;
  ULONG               Flags;
  ULONG               FrameID;
  FLT_FILESYSTEM_TYPE FileSystemType;
  USHORT              FilterVolumeNameLength;
  WCHAR               FilterVolumeName[1];
} FILTER_VOLUME_STANDARD_INFORMATION, *PFILTER_VOLUME_STANDARD_INFORMATION;
````


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

Read-only member used to identify the type of file system being used on the volume.  The possible values for this member are listed in <a href="..\fltuserstructures\ne-fltuserstructures-_flt_filesystem_type.md">FLT_FILESYSTEM_TYPE</a>.


### -field FilterVolumeNameLength

Read-only length, in bytes, of the volume name.


### -field FilterVolumeName

Read-only name of the volume of <b>FilterVolumeNameLength</b> length.  This Unicode string is not NULL-terminated.


## -remarks



Filter manager enumeration routines, such as <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>, can fill a buffer with structures of type FILTER_VOLUME_STANDARD_INFORMATION where each structure represents a volume known to filter manager.  This list of structures  can contain multiple volumes with the same name.  For more information, see <a href="https://msdn.microsoft.com/c05982dc-4124-4f9a-93b8-0e56ac296d1b">Understanding Volume Enumerations with Duplicate Volume Names</a>.

The FILTER_VOLUME_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry falls on an 8-byte boundary.

A FILTER_VOLUME_STANDARD_INFORMATION structure can be allocated from paged or nonpaged pool.




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541522">FilterVolumeFindClose</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_volume_basic_information.md">FILTER_VOLUME_BASIC_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumes.md">FltEnumerateVolumes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541530">FilterVolumeFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541525">FilterVolumeFindFirst</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILTER_VOLUME_STANDARD_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

