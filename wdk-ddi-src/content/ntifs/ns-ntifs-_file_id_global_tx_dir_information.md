---
UID: NS:ntifs._FILE_ID_GLOBAL_TX_DIR_INFORMATION
title: "_FILE_ID_GLOBAL_TX_DIR_INFORMATION"
author: windows-driver-content
description: The FILE_ID_GLOBAL_TX_DIR_INFORMATION structure contains information about transactional visibility for the files in a directory.
old-location: ifsk\file_id_global_tx_dir_information.htm
old-project: ifsk
ms.assetid: 4c4a0458-8ab3-4ef0-b455-c7a70737f322
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PFILE_ID_GLOBAL_TX_DIR_INFORMATION, FILE_ID_GLOBAL_TX_DIR_INFORMATION structure [Installable File System Drivers], PFILE_ID_GLOBAL_TX_DIR_INFORMATION structure pointer [Installable File System Drivers], ifsk.file_id_global_tx_dir_information, ntifs/PFILE_ID_GLOBAL_TX_DIR_INFORMATION, *PFILE_ID_GLOBAL_TX_DIR_INFORMATION, FILE_ID_GLOBAL_TX_DIR_INFORMATION, _FILE_ID_GLOBAL_TX_DIR_INFORMATION, ntifs/FILE_ID_GLOBAL_TX_DIR_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
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
-	FILE_ID_GLOBAL_TX_DIR_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_ID_GLOBAL_TX_DIR_INFORMATION, *PFILE_ID_GLOBAL_TX_DIR_INFORMATION
---

# _FILE_ID_GLOBAL_TX_DIR_INFORMATION structure


## -description


The <b>FILE_ID_GLOBAL_TX_DIR_INFORMATION</b> structure contains information about transactional visibility for the files in a directory.


## -syntax


````
typedef struct _FILE_ID_GLOBAL_TX_DIR_INFORMATION {
  ULONG          NextEntryOffset;
  ULONG          FileIndex;
  LARGE_INTEGER  CreationTime;
  LARGE_INTEGER  LastAccessTime;
  LARGE_INTEGER  LastWriteTime;
  LARGE_INTEGER  ChangeTime;
  LARGE_INTEGER  EndOfFile;
  LARGE_INTEGER  AllocationSize;
  ULONG          FileAttributes;
  ULONG          FileNameLength;
  LARGE_INTEGER  FileId;
  GUID           LockingTransactionId;
  ULONG          TxInfoFlags;
  WCHAR          FileName[1];
} FILE_ID_GLOBAL_TX_DIR_INFORMATION, *PFILE_ID_GLOBAL_TX_DIR_INFORMATION;
````


## -struct-fields




### -field NextEntryOffset


The byte offset from the beginning of this entry, at which the next FILE_ID_FULL_DIR_INFORMATION entry is located if multiple entries are present in a buffer. A value of zero indicates no other entries follow this one. 



### -field FileIndex


The byte offset of the file within the parent directory. For file systems in which the position of a file within the parent directory is not fixed and can be changed to maintain sort order, this field should be set to 0 and is ignored.



### -field CreationTime

The time when the file was created. 



### -field LastAccessTime


The last time the file was accessed.



### -field LastWriteTime


The last time information was written to the file.



### -field ChangeTime



The last time the file was changed.



### -field EndOfFile


The absolute new end-of-file position as a byte offset from the start of the file. EndOfFile specifies the offset to the byte immediately following the last valid byte in the file. 



### -field AllocationSize


The file allocation size in bytes. The value of this field is an integer multiple of the cluster size.



### -field FileAttributes

The file attributes.


<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>FILE_ATTRIBUTE_NORMAL</td>
<td> A file that has standard attributes should be created. </td>
</tr>
<tr>
<td>FILE_ATTRIBUTE_READONLY</td>
<td> A read-only file should be created. 
</td>
</tr>
<tr>
<td>FILE_ATTRIBUTE_HIDDEN</td>
<td> A hidden file should be created. 
</td>
</tr>
<tr>
<td>FILE_ATTRIBUTE_SYSTEM</td>
<td> A system file should be created. 
</td>
</tr>
<tr>
<td>FILE_ATTRIBUTE_ARCHIVE</td>
<td> The file should be marked so that it will be archived. 
</td>
</tr>
<tr>
<td>FILE_ATTRIBUTE_TEMPORARY</td>
<td> A temporary file should be created.
</td>
</tr>
</table>
 




### -field FileNameLength

 
The length, in bytes, of the file name contained within the <b>FileName</b> member.



### -field FileId

 
A file reference number for the file. The file system generates this number and assigns it to the file. For file systems that do not support <b>FileId</b>, this field is set to 0 and ignored.



### -field LockingTransactionId

 
A GUID value of the transaction that has this file locked for modification. The file system generates and assigns this value. 



### -field TxInfoFlags

A bitwise OR of zero or more of the following values. 

<table>
<tr>
<th>Value </th>
<th>Meaning </th>
</tr>
<tr>
<td>FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_WRITELOCKED
0x00000001
</td>
<td>The file is locked for modification by a transaction. 
The transaction's ID must be contained in the <b>LockingTransactionId</b> member if this flag is set.
</td>
</tr>
<tr>
<td>FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_VISIBLE_TO_TX
0x00000002
</td>
<td>The file is visible to transacted enumerators of the directory whose transaction ID is in the <b>LockingTransactionId</b> member.</td>
</tr>
<tr>
<td>FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_VISIBLE_OUTSIDE_TX
0x00000004
</td>
<td>The file is visible to transacted enumerators of the directory other than the one whose transaction ID is in the <b>LockingTransactionId</b> member, and it is visible to non-transacted enumerators of the directory.</td>
</tr>
</table>
 

If the FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_WRITELOCKED flag is not set, the other flags must not be set. If flags other than FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_WRITELOCKED are set, the FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_WRITELOCKED flag must be set.


### -field FileName


A sequence of Unicode characters containing the file name. 


<div class="alert"><b>Note</b>  Use <b>FileNameLength</b> to determine the length of the file name rather than assuming the presence of a trailing null delimiter.</div>
<div> </div>

## -remarks



The <b>FILE_ID_GLOBAL_TX_DIR_INFORMATION</b> structure can be implemented for file systems that return the FILE_SUPPORTS_TRANSACTIONS flag in response to a query using a <a href="..\ntifs\ns-ntifs-_file_fs_attribute_information.md">FILE_FS_ATTRIBUTE_INFORMATION</a> structure. It must not be implemented for file systems that do not return that flag.
  

If the FILE_ID_GLOBAL_TX_DIR_INFO_FLAG_WRITELOCKED flag is not set in <b>TxInfoFlags</b>, <b>LockingTransactionId</b> is ignored.



