---
UID: NS:ntifs._FILE_NAMES_INFORMATION
title: "_FILE_NAMES_INFORMATION"
author: windows-driver-content
description: A FILE_NAMES_INFORMATION structure used to query detailed information about the names of files in a directory.
old-location: ifsk\file_names_information.htm
old-project: ifsk
ms.assetid: a9eb4606-fe55-4f77-914a-656ebe247066
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PFILE_NAMES_INFORMATION structure pointer [Installable File System Drivers], ntifs/PFILE_NAMES_INFORMATION, *PFILE_NAMES_INFORMATION, FILE_NAMES_INFORMATION structure [Installable File System Drivers], FILE_NAMES_INFORMATION, ifsk.file_names_information, _FILE_NAMES_INFORMATION, PFILE_NAMES_INFORMATION, ntifs/FILE_NAMES_INFORMATION, fileinformationstructures_8349a2eb-ffeb-4050-9084-b09474079415.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FILE_NAMES_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILE_NAMES_INFORMATION, FILE_NAMES_INFORMATION"
---

# _FILE_NAMES_INFORMATION structure


## -description


A FILE_NAMES_INFORMATION structure used to query detailed information about the names of files in a directory. 


## -syntax


````
typedef struct _FILE_NAMES_INFORMATION {
  ULONG NextEntryOffset;
  ULONG FileIndex;
  ULONG FileNameLength;
  WCHAR FileName[1];
} FILE_NAMES_INFORMATION, *PFILE_NAMES_INFORMATION;
````


## -struct-fields




#### - NextEntryOffset

Byte offset for the next FILE_NAMES_INFORMATION entry, if multiple entries are present in a buffer. This member is zero if no other entries follow this one. 


#### - FileIndex

Byte offset of the file within the parent directory. This member is undefined for file systems, such as NTFS, in which the position of a file within the parent directory is not fixed and can be changed at any time to maintain sort order. 


#### - FileNameLength

Specifies the length of the file name string. 


#### - FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string. 


## -remarks


This information can be queried in either of the following ways: 
<ul>
<li>
Call <a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>, passing FileNamesInformation as the value of <i>FileInformationClass</i> and passing a caller-allocated, FILE_NAMES_INFORMATION-structured buffer as the value of <i>FileInformation</i>. 

</li>
<li>
Create an IRP with major function code IRP_MJ_DIRECTORY_CONTROL and minor function code IRP_MN_QUERY_DIRECTORY. 

</li>
</ul>No specific access rights are required to query this information. 

This structure must be aligned on a LONG (4-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on a 4-byte boundary. 



## -see-also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullchangedirectory~r9.md">FsRtlNotifyFullChangeDirectory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>

<a href="..\ntifs\nf-ntifs-zwquerydirectoryfile.md">ZwQueryDirectoryFile</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_NAMES_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

