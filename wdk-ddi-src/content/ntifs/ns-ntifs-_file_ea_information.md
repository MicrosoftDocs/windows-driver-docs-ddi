---
UID: NS:ntifs._FILE_EA_INFORMATION
title: "_FILE_EA_INFORMATION"
author: windows-driver-content
description: The FILE_EA_INFORMATION structure is used to query for the size of the extended attributes (EA) for a file.
old-location: kernel\file_ea_information.htm
old-project: kernel
ms.assetid: 1b27f26f-c98d-4979-b60e-0ed5965f637c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_EA_INFORMATION, FILE_EA_INFORMATION structure [Kernel-Mode Driver Architecture], FILE_EA_INFORMATION, kernel.file_ea_information, kstruct_b_f78f051a-aa8f-4611-a699-1f706ac74f1f.xml, PFILE_EA_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_EA_INFORMATION, ntifs/FILE_EA_INFORMATION, ntifs/PFILE_EA_INFORMATION, PFILE_EA_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows XP and later versions of Windows.
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
-	Ntifs.h
apiname:
-	FILE_EA_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_EA_INFORMATION, *PFILE_EA_INFORMATION
---

# _FILE_EA_INFORMATION structure


## -description


The <b>FILE_EA_INFORMATION</b> structure is used to query for the size of the extended attributes (EA) for a file.


## -syntax


````
typedef struct _FILE_EA_INFORMATION {
  ULONG EaSize;
} FILE_EA_INFORMATION, *PFILE_EA_INFORMATION;
````


## -struct-fields




### -field EaSize

Specifies the combined length, in bytes, of the extended attributes for the file.


## -remarks



This structure is used by the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> routine.

An extended attribute is a piece of application-specific metadata that an application can associate with a file that is not part of the file's data. In addition to the built-in attributes of a file, such as creation and modification times, applications can add non-file system attributes, such as the author's name and a description of the file content.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_EA_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

