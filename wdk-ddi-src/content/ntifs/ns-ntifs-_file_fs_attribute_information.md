---
UID: NS:ntifs._FILE_FS_ATTRIBUTE_INFORMATION
title: "_FILE_FS_ATTRIBUTE_INFORMATION"
author: windows-driver-content
description: The FILE_FS_ATTRIBUTE_INFORMATION structure is used to query attribute information for a file system.
old-location: ifsk\file_fs_attribute_information.htm
old-project: ifsk
ms.assetid: 373788d8-4963-4319-82ae-3a0675c9fff4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_FS_ATTRIBUTE_INFORMATION, FILE_FS_ATTRIBUTE_INFORMATION, FILE_FS_ATTRIBUTE_INFORMATION structure [Installable File System Drivers], PFILE_FS_ATTRIBUTE_INFORMATION, PFILE_FS_ATTRIBUTE_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_ATTRIBUTE_INFORMATION, fileinformationstructures_d3a65f15-7f98-492d-a65e-65db56c4c58d.xml, ifsk.file_fs_attribute_information, ntifs/FILE_FS_ATTRIBUTE_INFORMATION, ntifs/PFILE_FS_ATTRIBUTE_INFORMATION"
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
-	FILE_FS_ATTRIBUTE_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_FS_ATTRIBUTE_INFORMATION, *PFILE_FS_ATTRIBUTE_INFORMATION
---

# _FILE_FS_ATTRIBUTE_INFORMATION structure


## -description


The <b>FILE_FS_ATTRIBUTE_INFORMATION</b> 
   structure is used to query attribute information for a file system.


## -struct-fields




### -field FileSystemAttributes

Bitmask of flags specifying attributes of the specified file system, as a compatible combination of the 
       following flags.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FILE_CASE_PRESERVED_NAMES</b>

</td>
<td>
The file system preserves the case of file names when it places a name on disk.

</td>
</tr>
<tr>
<td>
<b>FILE_CASE_SENSITIVE_SEARCH</b>

</td>
<td>
The file system supports case-sensitive file names.

</td>
</tr>
<tr>
<td>
<b>FILE_FILE_COMPRESSION</b>

</td>
<td>
The file system supports file-based compression. This flag is incompatible with the 
          <b>FILE_VOLUME_IS_COMPRESSED</b> flag.

</td>
</tr>
<tr>
<td>
<b>FILE_NAMED_STREAMS</b>

</td>
<td>
The file system supports named streams.

</td>
</tr>
<tr>
<td>
<b>FILE_PERSISTENT_ACLS</b>

</td>
<td>
The file system preserves and enforces access control lists 
          (<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>).

</td>
</tr>
<tr>
<td>
<b>FILE_READ_ONLY_VOLUME</b>

</td>
<td>
<b>Microsoft Windows XP and later:</b> The specified volume is read-only.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_ENCRYPTION</b>

</td>
<td>
The file system supports the Encrypted File System (EFS).

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_OBJECT_IDS</b>

</td>
<td>
The file system supports object identifiers.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_REMOTE_STORAGE</b>

</td>
<td>
The file system supports remote storage.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_REPARSE_POINTS</b>

</td>
<td>
The file system supports reparse points.

</td>
</tr>
<tr>
<td>
<b>FILE_SUPPORTS_SPARSE_FILES</b>

</td>
<td>
The file system supports sparse files.

</td>
</tr>
<tr>
<td>
<b>FILE_UNICODE_ON_DISK</b>

</td>
<td>
The file system supports Unicode in file names.

</td>
</tr>
<tr>
<td>
<b>FILE_VOLUME_IS_COMPRESSED</b>

</td>
<td>
The specified volume is a compressed volume. This flag is incompatible with the 
          <b>FILE_FILE_COMPRESSION</b> flag.

</td>
</tr>
<tr>
<td>
<b>FILE_VOLUME_QUOTAS</b>

</td>
<td>
The file system supports per-user quotas.

</td>
</tr>
</table>
 


### -field MaximumComponentNameLength

Maximum file name component length, in bytes, supported by the specified file system. A file name component 
      is that portion of a file name between backslashes.


### -field FileSystemNameLength

Length, in bytes, of the file system name.


### -field FileSystemName

File system name.


## -remarks



This information can be queried in either of the following ways:

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a> or 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>, passing 
       <b>FileFsAttributeInformation</b> as the value of 
       <i>FileInformationClass</i> and passing a caller-allocated, 
       <b>FILE_FS_ATTRIBUTE_INFORMATION</b>-structured 
       buffer as the value of <i>FileInformation</i>.

On CSVFS <b>FileFsAttributeInformation</b> returns 
       <b>FILE_FS_ATTRIBUTE_INFORMATION</b> for the 
       CSVFS file system. If you want to query <b>FileFsAttributeInformation</b> for the file 
       system CSVFS is layered on then you should use 
       <a href="https://msdn.microsoft.com/1AC3FD47-70B8-4735-9B25-A8B2BAEE5A83">FSCTL_CSV_QUERY_DOWN_LEVEL_FILE_SYSTEM_CHARACTERISTICS</a>.

</li>
<li>
Create an IRP with major function code 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>.

</li>
</ul>
No specific access rights are required to query this information. Thus this information is available as long as 
     the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume.

The size of the buffer passed in the <i>FileInformation</i> parameter to 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a> or 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a> must be at 
     least <code>sizeof(FILE_FS_ATTRIBUTE_INFORMATION)</code>.

This structure must be aligned on a <b>LONG</b> (4-byte) boundary.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543443">FltQueryVolumeInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549318">IRP_MJ_QUERY_VOLUME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567070">ZwQueryVolumeInformationFile</a>
 

 

