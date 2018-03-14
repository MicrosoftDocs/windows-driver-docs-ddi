---
UID: NS:ntifs._FILE_LINK_INFORMATION
title: "_FILE_LINK_INFORMATION"
author: windows-driver-content
description: The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file.
old-location: ifsk\file_link_information.htm
old-project: ifsk
ms.assetid: c0c47dc7-d672-4094-af17-9de2b01886aa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_LINK_INFORMATION, FILE_LINK_INFORMATION, FILE_LINK_INFORMATION structure [Installable File System Drivers], PFILE_LINK_INFORMATION, PFILE_LINK_INFORMATION structure pointer [Installable File System Drivers], _FILE_LINK_INFORMATION, fileinformationstructures_6702855e-5076-41aa-a6c8-e9569c782646.xml, ifsk.file_link_information, ntifs/FILE_LINK_INFORMATION, ntifs/PFILE_LINK_INFORMATION"
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
-	FILE_LINK_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION
---

# _FILE_LINK_INFORMATION structure


## -description


The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. 


## -syntax


````
typedef struct _FILE_LINK_INFORMATION {
  BOOLEAN ReplaceIfExists;
  HANDLE  RootDirectory;
  ULONG   FileNameLength;
  WCHAR   FileName[1];
} FILE_LINK_INFORMATION, *PFILE_LINK_INFORMATION;
````


## -struct-fields




### -field ReplaceIfExists

Set to <b>TRUE</b> to specify that if the link already exists, it should be replaced with the new link. Set to <b>FALSE</b> if the link creation operation should fail if the link already exists. 


### -field RootDirectory

If the link is to be created in the same directory as the file that is being linked to, or if the <b>FileName</b> member contains the full pathname for the link to be created, this is <b>NULL</b>. Otherwise it is a handle for the directory where the link is to be created. 


### -field FileNameLength

Length, in bytes, of the file name string. 


### -field FileName

The first character of the name to be assigned to the newly created link. This is followed in memory by the remainder of the string. If the <b>RootDirectory</b> member is <b>NULL</b> and the link is to be created in a different directory from the file that is being linked to, this member specifies the full pathname for the link to be created. Otherwise, it specifies only the file name. (See the Remarks section for <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> for details on the syntax of this file name string.) 


## -remarks



The FILE_LINK_INFORMATION structure is used to create an NTFS hard link to an existing file. This operation can be performed in either of the following ways: 

<ul>
<li>
Call <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a> or <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, passing FileLinkInformation as the value of FileInformationClass and passing a caller-allocated, FILE_LINK_INFORMATION-structured buffer as the value of <i>FileInformation</i>. The <i>FileHandle</i> parameter specifies the existing file to which the hard link should point. 

</li>
<li>
Create an IRP with major function code IRP_MJ_SET_INFORMATION. 

</li>
</ul>
No specific access rights are required to set this information. 

File system minifilters must use <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>, not <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, to set this information for a file. 

For more information about NTFS hard links, see the Microsoft Windows SDK documentation for the Win32 <b>CreateHardLink</b> function. 

The size of the <i>FileInformation</i> buffer passed to <a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a> or <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> must be at least <b>sizeof</b>(FILE_LINK_INFORMATION). 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="..\fltkernel\nf-fltkernel-fltsetinformationfile.md">FltSetInformationFile</a>



<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549366">IRP_MJ_SET_INFORMATION</a>



 

 


