---
UID: NS:ntifs._FILE_ID_BOTH_DIR_INFORMATION
title: "_FILE_ID_BOTH_DIR_INFORMATION"
author: windows-driver-content
description: The FILE_ID_BOTH_DIR_INFORMATION structure is used to query file reference number information for the files in a directory.
old-location: ifsk\file_id_both_dir_information.htm
old-project: ifsk
ms.assetid: 57a66b41-f9f6-42e1-95d7-010cacd1374a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_ID_BOTH_DIR_INFORMATION, FILE_ID_BOTH_DIR_INFORMATION, FILE_ID_BOTH_DIR_INFORMATION structure [Installable File System Drivers], PFILE_ID_BOTH_DIR_INFORMATION, PFILE_ID_BOTH_DIR_INFORMATION structure pointer [Installable File System Drivers], _FILE_ID_BOTH_DIR_INFORMATION, fileinformationstructures_e4d079c2-5491-4692-bdf2-a6f356bdf431.xml, ifsk.file_id_both_dir_information, ntifs/FILE_ID_BOTH_DIR_INFORMATION, ntifs/PFILE_ID_BOTH_DIR_INFORMATION"
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
-	FILE_ID_BOTH_DIR_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_ID_BOTH_DIR_INFORMATION, *PFILE_ID_BOTH_DIR_INFORMATION
---

# _FILE_ID_BOTH_DIR_INFORMATION structure


## -description


The FILE_ID_BOTH_DIR_INFORMATION structure is used to query file reference number information for the files in a directory. 


## -struct-fields




### -field NextEntryOffset

Byte offset of the next FILE_ID_BOTH_DIR_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


### -field FileIndex

Byte offset of the file within the parent directory. This member is undefined for file systems, such as NTFS, in which the position of a file within the parent directory is not fixed and can be changed at any time to maintain sort order. 


### -field CreationTime

Time when the file was created. 


### -field LastAccessTime

Last time the file was accessed. 


### -field LastWriteTime

Last time information was written to the file. 


### -field ChangeTime

Last time the file was changed. 


### -field EndOfFile

Absolute new end-of-file position as a byte offset from the start of the file. <b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file. In other words, <b>EndOfFile</b> is the offset to the byte immediately following the last valid byte in the file.


### -field AllocationSize

File allocation size, in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device. 


### -field FileAttributes

File attributes, which can be any valid combination of the following: 


<dl>
<dd>FILE_ATTRIBUTE_READONLY</dd>
<dd>FILE_ATTRIBUTE_HIDDEN</dd>
<dd>FILE_ATTRIBUTE_SYSTEM</dd>
<dd>FILE_ATTRIBUTE_DIRECTORY</dd>
<dd>FILE_ATTRIBUTE_ARCHIVE</dd>
<dd>FILE_ATTRIBUTE_NORMAL</dd>
<dd>FILE_ATTRIBUTE_TEMPORARY</dd>
<dd>FILE_ATTRIBUTE_COMPRESSED</dd>
</dl>



### -field FileNameLength

Specifies the length of the file name string. 


### -field EaSize

Combined length, in bytes, of the extended attributes (EA) for the file. 


### -field ShortNameLength

Specifies the length of the short file name string. 


### -field ShortName

Unicode string containing the short (8.3) name for the file. 


### -field FileId

The 8-byte file reference number for the file. This number is generated and assigned to the file by the file system. (Note that the <b>FileId</b> is not the same as the 16-byte "file object ID" that was added to NTFS for Microsoft Windows 2000.) 


### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string. 


## -remarks



This information can be queried in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>, passing FileIdBothDirectoryInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_ID_BOTH_DIR_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>
No specific access rights are required to query this information. 

File reference numbers, also called file IDs, are guaranteed to be unique only within a static file system. They are not guaranteed to be unique over time, because file systems are free to reuse them. Nor are they guaranteed to remain constant. For example, the FAT file system generates the file reference number for a file from the byte offset of the file's directory entry record (DIRENT) on the disk. Defragmentation can change this byte offset. Thus a FAT file reference number can change over time. 

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547026">FsRtlNotifyFullChangeDirectory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567047">ZwQueryDirectoryFile</a>
 

 

