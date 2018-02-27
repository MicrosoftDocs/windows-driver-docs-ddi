---
UID: NS:ntifs._FILE_LINK_ENTRY_INFORMATION
title: "_FILE_LINK_ENTRY_INFORMATION"
author: windows-driver-content
description: The FILE_LINK_ENTRY_INFORMATION structure describes a single NTFS hard link to an existing file.
old-location: ifsk\file_link_entry_information.htm
old-project: ifsk
ms.assetid: b42edb45-3f4f-4f65-aede-8f51149dda78
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_LINK_ENTRY_INFORMATION, FILE_LINK_ENTRY_INFORMATION, FILE_LINK_ENTRY_INFORMATION structure [Installable File System Drivers], PFILE_LINK_ENTRY_INFORMATION, PFILE_LINK_ENTRY_INFORMATION structure pointer [Installable File System Drivers], _FILE_LINK_ENTRY_INFORMATION, ifsk.file_link_entry_information, ntifs/FILE_LINK_ENTRY_INFORMATION, ntifs/PFILE_LINK_ENTRY_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
-	FILE_LINK_ENTRY_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_LINK_ENTRY_INFORMATION, *PFILE_LINK_ENTRY_INFORMATION
---

# _FILE_LINK_ENTRY_INFORMATION structure


## -description


The <b>FILE_LINK_ENTRY_INFORMATION</b> structure describes a single NTFS hard link to an existing file.


## -syntax


````
typedef struct _FILE_LINK_ENTRY_INFORMATION {
  ULONG    NextEntryOffset;
  LONGLONG ParentFileId;
  ULONG    FileNameLength;
  WCHAR    FileName;
} FILE_LINK_ENTRY_INFORMATION, *PFILE_LINK_ENTRY_INFORMATION;
````


## -struct-fields




### -field NextEntryOffset

The offset, in bytes, to the next <b>FILE_LINK_ENTRY_INFORMATION</b> structure, or 0 if the current structure is the last  <b>FILE_LINK_ENTRY_INFORMATION</b> structure.


### -field ParentFileId

The ID of the parent directory of the link.


### -field FileNameLength

The length, in characters, of the <b>FileName</b> for the link.


### -field FileName

The name of the link.


## -see-also

<a href="..\ntifs\ns-ntifs-_file_links_information.md">FILE_LINKS_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_LINK_ENTRY_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

