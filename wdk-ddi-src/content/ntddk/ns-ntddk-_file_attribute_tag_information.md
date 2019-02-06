---
UID: NS:ntddk._FILE_ATTRIBUTE_TAG_INFORMATION
title: _FILE_ATTRIBUTE_TAG_INFORMATION (ntddk.h)
description: The FILE_ATTRIBUTE_TAG_INFORMATION structure is used as an argument to ZwQueryInformationFile.
old-location: kernel\file_attribute_tag_information.htm
tech.root: kernel
ms.assetid: e330bd79-cd44-412e-b9aa-ca5b791750d4
ms.date: 04/30/2018
ms.keywords: "*PFILE_ATTRIBUTE_TAG_INFORMATION, FILE_ATTRIBUTE_TAG_INFORMATION, FILE_ATTRIBUTE_TAG_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ATTRIBUTE_TAG_INFORMATION, PFILE_ATTRIBUTE_TAG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ATTRIBUTE_TAG_INFORMATION, kernel.file_attribute_tag_information, kstruct_b_d990c73e-3b75-4c00-954d-a16cca892895.xml, ntddk/FILE_ATTRIBUTE_TAG_INFORMATION, ntddk/PFILE_ATTRIBUTE_TAG_INFORMATION"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
-	Ntddk.h
api_name:
-	FILE_ATTRIBUTE_TAG_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_ATTRIBUTE_TAG_INFORMATION, *PFILE_ATTRIBUTE_TAG_INFORMATION
---

# _FILE_ATTRIBUTE_TAG_INFORMATION structure


## -description


The <b>FILE_ATTRIBUTE_TAG_INFORMATION</b> structure is used as an argument to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>. 


## -struct-fields




### -field FileAttributes

Specifies one or more FILE_ATTRIBUTE_<i>XXX</i> flags. For descriptions of these flags, see the documentation of the <b>GetFileAttributes</b> function in the Microsoft Windows SDK.


### -field ReparseTag

Specifies the reparse point tag. If the <b>FileAttributes</b> member includes the FILE_ATTRIBUTE_REPARSE_POINT attribute flag, this member specifies the reparse tag. Otherwise, this member is unused.


## -remarks



FILE_READ_ATTRIBUTES access to the file is required to query this information.

For more information about reparse points and reparse point tags, see the Windows SDK.

This structure must be aligned on a LONG (4-byte) boundary.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
 

 

