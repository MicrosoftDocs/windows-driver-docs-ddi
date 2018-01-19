---
UID: NS:ntifs._FILE_DIRECTORY_INFORMATION
title: _FILE_DIRECTORY_INFORMATION
author: windows-driver-content
description: The FILE_DIRECTORY_INFORMATION structure is used to query detailed information for the files in a directory.
old-location: ifsk\file_directory_information.htm
old-project: ifsk
ms.assetid: 012c3178-f3a0-449b-b4a2-91fff4af1a17
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _FILE_DIRECTORY_INFORMATION, FILE_DIRECTORY_INFORMATION, *PFILE_DIRECTORY_INFORMATION
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
req.alt-api: FILE_DIRECTORY_INFORMATION
req.alt-loc: ntifs.h
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
req.typenames: FILE_DIRECTORY_INFORMATION, *PFILE_DIRECTORY_INFORMATION
---

# _FILE_DIRECTORY_INFORMATION structure



## -description
The FILE_DIRECTORY_INFORMATION structure is used to query detailed information for the files in a directory. 



## -syntax

````
typedef struct _FILE_DIRECTORY_INFORMATION {
  ULONG         NextEntryOffset;
  ULONG         FileIndex;
  LARGE_INTEGER CreationTime;
  LARGE_INTEGER LastAccessTime;
  LARGE_INTEGER LastWriteTime;
  LARGE_INTEGER ChangeTime;
  LARGE_INTEGER EndOfFile;
  LARGE_INTEGER AllocationSize;
  ULONG         FileAttributes;
  ULONG         FileNameLength;
  WCHAR         FileName[1];
} FILE_DIRECTORY_INFORMATION, *PFILE_DIRECTORY_INFORMATION;
````


## -struct-fields

### -field NextEntryOffset

Byte offset of the next FILE_DIRECTORY_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


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


### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string. 


## -remarks
This information can be queried in either of the following ways: 

Call <a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>, passing FileDirectoryInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_DIRECTORY_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY. 

No specific access rights are required to query this information. 

All dates and times are in absolute system-time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601. 

This structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. 


## -see-also
<dl>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtlnotifyfullchangedirectory.md">FsRtlNotifyFullChangeDirectory</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_DIRECTORY_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

