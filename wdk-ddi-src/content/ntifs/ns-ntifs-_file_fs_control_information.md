---
UID: NS:ntifs._FILE_FS_CONTROL_INFORMATION
title: "_FILE_FS_CONTROL_INFORMATION"
author: windows-driver-content
description: The FILE_FS_CONTROL_INFORMATION structure is used to query or set control information for the files in a directory.
old-location: ifsk\file_fs_control_information.htm
old-project: ifsk
ms.assetid: 8a7e136a-fc87-481c-bb35-270408cb5071
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILE_FS_CONTROL_INFORMATION, FILE_FS_CONTROL_INFORMATION, FILE_FS_CONTROL_INFORMATION structure [Installable File System Drivers], PFILE_FS_CONTROL_INFORMATION, PFILE_FS_CONTROL_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_CONTROL_INFORMATION, fileinformationstructures_387e4fd0-c3a2-4472-b29d-79f8a5d876f8.xml, ifsk.file_fs_control_information, ntifs/FILE_FS_CONTROL_INFORMATION, ntifs/PFILE_FS_CONTROL_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FILE_FS_CONTROL_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_CONTROL_INFORMATION, *PFILE_FS_CONTROL_INFORMATION
---

# _FILE_FS_CONTROL_INFORMATION structure


## -description


The FILE_FS_CONTROL_INFORMATION structure is used to query or set control information for the files in a directory. 


## -struct-fields




### -field FreeSpaceStartFiltering

Minimum amount of free disk space, in bytes, that is required for the Content-Indexing daemon to begin document filtering. 


### -field FreeSpaceThreshold

Minimum amount of free disk space, in bytes, required for the Indexing Service to continue to filter documents and merge word lists. If the amount of free disk space falls below this threshold, a warning message is written to the Microsoft Windows application event log. Filtering and merging are halted until space is freed. 


### -field FreeSpaceStopFiltering

Minimum amount of free disk space, in bytes, that is required for the Content-Indexing daemon to continue document filtering. If the amount of free disk space falls below this threshold, document filtering is halted. 


### -field DefaultQuotaThreshold

Default per-user disk quota warning threshold for the volume. 


### -field DefaultQuotaLimit

Default per-user disk quota limit for the volume. 


### -field FileSystemControlFlags

Bitmask of flags that control quota enforcement and logging of user-related quota events on the volume. Logging makes an entry in the Windows application event log. Compatible combination of one or more of the following: 

<table>
<tr>
<th>File System Control Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_VC_CONTENT_INDEX_DISABLED

</td>
<td>
If set, content indexing is disabled. 

</td>
</tr>
<tr>
<td>
FILE_VC_LOG_QUOTA_LIMIT

</td>
<td>
If set, an event log entry will be created when the user exceeds his or her assigned disk quota limit. 

</td>
</tr>
<tr>
<td>
FILE_VC_LOG_QUOTA_THRESHOLD

</td>
<td>
If set, an event log entry will be created when the user exceeds his or her assigned quota warning threshold. 

</td>
</tr>
<tr>
<td>
FILE_VC_LOG_VOLUME_LIMIT

</td>
<td>
If set, an event log entry will be created when the volume's free space limit is exceeded. 

</td>
</tr>
<tr>
<td>
FILE_VC_LOG_VOLUME_THRESHOLD

</td>
<td>
If set, an event log entry will be created when the volume's free space threshold is exceeded. 

</td>
</tr>
<tr>
<td>
FILE_VC_QUOTA_ENFORCE

</td>
<td>
If set, quotas are enforced on the volume. 

</td>
</tr>
<tr>
<td>
FILE_VC_QUOTA_TRACK

</td>
<td>
If set, quotas are tracked on the volume. 

</td>
</tr>
<tr>
<td>
FILE_VC_QUOTAS_INCOMPLETE

</td>
<td>
If set, the quota information for the volume is incomplete. 

</td>
</tr>
<tr>
<td>
FILE_VC_QUOTAS_REBUILDING

</td>
<td>
If set, the file system is rebuilding the quota information for the volume. 

</td>
</tr>
</table>
 

In addition, the following flag masks are defined. These are useful for testing flag values. 

<table>
<tr>
<th>Mask</th>
<th>Value</th>
</tr>
<tr>
<td>
FILE_VC_QUOTA_MASK

</td>
<td>
FILE_VC_QUOTA_ENFORCE | FILE_VC_QUOTA_TRACK

</td>
</tr>
<tr>
<td>
FILE_VC_QUOTA_NONE

</td>
<td>
~FILE_VC_QUOTA_ENFORCE &amp; ~FILE_VC_QUOTA_TRACK

</td>
</tr>
<tr>
<td>
FILE_VC_VALID_MASK

</td>
<td>
ORed combination of all flags in the above table. 

</td>
</tr>
</table>
 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, passing FileFsControlInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_CONTROL_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION. 

</li>
</ul>
FILE_READ_DATA access to the volume is required to query this information. 

This information can be set in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544564">FltSetVolumeInformation</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a>, passing FileFsControlInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_FS_CONTROL_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION. 

</li>
</ul>
FILE_WRITE_DATA access to the volume is required to set this information. 

The size of the buffer passed in the <i>FileInformation</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544564">FltSetVolumeInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, or <b>ZwSetVolumeInformationFile</b> must be at least <b>sizeof</b> (FILE_FS_CONTROL_INFORMATION). 

This structure must be aligned on a LONGLONG (8-byte) boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544564">FltSetVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549415">IRP_MJ_SET_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567112">ZwSetVolumeInformationFile</a>
 

 

