---
UID: NS:ntifs._FILE_LINK_INFORMATION
title: "_FILE_LINK_INFORMATION"
description: The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file.
old-location: ifsk\file_link_information.htm
tech.root: ifsk
ms.assetid: c0c47dc7-d672-4094-af17-9de2b01886aa
ms.date: 04/16/2018
ms.keywords: "*PFILE_LINK_INFORMATION, FILE_LINK_INFORMATION, FILE_LINK_INFORMATION structure [Installable File System Drivers], PFILE_LINK_INFORMATION, PFILE_LINK_INFORMATION structure pointer [Installable File System Drivers], _FILE_LINK_INFORMATION, fileinformationstructures_6702855e-5076-41aa-a6c8-e9569c782646.xml, ifsk.file_link_information, ntifs/FILE_LINK_INFORMATION, ntifs/PFILE_LINK_INFORMATION"
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
-	FILE_LINK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION
---

# _FILE_LINK_INFORMATION structure


## -description


The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. 

## -syntax
```cpp
typedef struct _FILE_LINK_INFORMATION {
#if (_WIN32_WINNT >= _WIN32_WINNT_WIN10_RS5)
    union {
        BOOLEAN ReplaceIfExists;  // FileLinkInformation
        ULONG Flags;              // FileLinkInformationEx
    } DUMMYUNIONNAME;
#else
    BOOLEAN ReplaceIfExists;
#endif
    HANDLE RootDirectory;
    ULONG FileNameLength;
    WCHAR FileName[1];
} FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION;

```



## -struct-fields


### -field DUMMYUNIONNAME.ReplaceIfExists

Set to <b>TRUE</b> to specify that if the link already exists, it should be replaced with the new link. Set to <b>FALSE</b> if the link creation operation should fail if the link already exists. 

### -field DUMMYUNIONNAME.Flags

Flags for the link operation.  This field is only applicable when used with the FileLinkInformationEx information class.

Here are the possible values:

| Value | Meaning |
| ----- | ------- |
| **FILE_LINK_REPLACE_IF_EXISTS**<br>0x00000001 | If a file with the given name already exists, it should be replaced with the new link.  Equivalent to the ReplaceIfExists field used with the FileLinkInformation information class. |
| **FILE_LINK_POSIX_SEMANTICS**<br>0x00000002 | If FILE_LINK_REPLACE_IF_EXISTS is also specified, allow replacing a file even if there are existing handles to it.  Existing handles to the replaced file continue to be valid for operations such as read and write.  Any subsequent opens of the target name will open the new link, not the replaced file. |
| **FILE_LINK_SUPPRESS_STORAGE_RESERVE_INHERITANCE**<br>0x00000008 | When creating a link in a new directory, suppress any inheritance rules related to the storage reserve ID property of the file. |
| **FILE_LINK_NO_INCREASE_AVAILABLE_SPACE**<br>0x00000010 | If FILE_LINK_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when creating a link in a new directory, automatically resize affected storage reserve areas to prevent the user visible free space on the volume from increasing.  Requires manage volume access. |
| **FILE_LINK_NO_DECREASE_AVAILABLE_SPACE**<br>0x00000020 | If FILE_LINK_SUPPRESS_STORAGE_RESERVE_INHERITANCE is not also specified, when creating a link in a new directory, automatically resize affected storage reserve areas to prevent the user visible free space on the volume from decreasing.  Requires manage volume access. |
| **FILE_LINK_PRESERVE_AVAILABLE_SPACE**<br>0x00000030 | Equivalent to specifying both FILE_LINK_NO_INCREASE_AVAILABLE_SPACE and FILE_LINK_NO_DECREASE_AVAILABLE_SPACE. |
| **FILE_LINK_IGNORE_READONLY_ATTRIBUTE**<br>0x00000040 | If FILE_LINK_REPLACE_IF_EXISTS is also specified, allow replacing a file even if it is read-only.  Requires WRITE_ATTRIBUTES access to the replaced file. |

### -field RootDirectory

If the link is to be created in the same directory as the file that is being linked to, or if the <b>FileName</b> member contains the full pathname for the link to be created, this is <b>NULL</b>. Otherwise it is a handle for the directory where the link is to be created. 


### -field FileNameLength

Length, in bytes, of the file name string. 


### -field FileName

The first character of the name to be assigned to the newly created link. This is followed in memory by the remainder of the string. If the <b>RootDirectory</b> member is <b>NULL</b> and the link is to be created in a different directory from the file that is being linked to, this member specifies the full pathname for the link to be created. Otherwise, it specifies only the file name. (See the Remarks section for <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> for details on the syntax of this file name string.) 


## -remarks



The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. This operation can be performed in either of the following ways: 

<ul>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>, passing FileLinkInformation as the value of FileInformationClass and passing a caller-allocated, FILE_LINK_INFORMATION-structured buffer as the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the existing file to which the hard link should point. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_INFORMATION. 

</li>
</ul>
No specific access rights are required to set this information. 

File system minifilters must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>, not <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>, to set this information for a file. 

For more information about NTFS hard links, see the Microsoft Windows SDK documentation for the Win32 <b>CreateHardLink</b> function. 

The size of the <i>FileInformation</i> buffer passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> must be at least <b>sizeof</b>(FILE_LINK_INFORMATION). 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

