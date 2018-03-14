---
UID: NS:ntddk._FILE_ATTRIBUTE_TAG_INFORMATION
title: "_FILE_ATTRIBUTE_TAG_INFORMATION"
author: windows-driver-content
description: The FILE_ATTRIBUTE_TAG_INFORMATION structure is used as an argument to ZwQueryInformationFile.
old-location: kernel\file_attribute_tag_information.htm
old-project: kernel
ms.assetid: e330bd79-cd44-412e-b9aa-ca5b791750d4
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PFILE_ATTRIBUTE_TAG_INFORMATION, FILE_ATTRIBUTE_TAG_INFORMATION, FILE_ATTRIBUTE_TAG_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ATTRIBUTE_TAG_INFORMATION, PFILE_ATTRIBUTE_TAG_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ATTRIBUTE_TAG_INFORMATION, kernel.file_attribute_tag_information, kstruct_b_d990c73e-3b75-4c00-954d-a16cca892895.xml, ntddk/FILE_ATTRIBUTE_TAG_INFORMATION, ntddk/PFILE_ATTRIBUTE_TAG_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	FILE_ATTRIBUTE_TAG_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_ATTRIBUTE_TAG_INFORMATION, *PFILE_ATTRIBUTE_TAG_INFORMATION
---

# _FILE_ATTRIBUTE_TAG_INFORMATION structure


## -description


The <b>FILE_ATTRIBUTE_TAG_INFORMATION</b> structure is used as an argument to <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>. 


## -syntax


````
typedef struct _FILE_ATTRIBUTE_TAG_INFORMATION {
  ULONG FileAttributes;
  ULONG ReparseTag;
} FILE_ATTRIBUTE_TAG_INFORMATION, *PFILE_ATTRIBUTE_TAG_INFORMATION;
````


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

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



 

 


