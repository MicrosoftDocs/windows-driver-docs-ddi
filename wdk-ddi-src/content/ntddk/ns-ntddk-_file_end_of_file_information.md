---
UID: NS:ntddk._FILE_END_OF_FILE_INFORMATION
title: "_FILE_END_OF_FILE_INFORMATION"
author: windows-driver-content
description: The FILE_END_OF_FILE_INFORMATION structure is used as an argument to the ZwSetInformationFile routine.
old-location: kernel\file_end_of_file_information.htm
old-project: kernel
ms.assetid: 9af172d9-2309-4731-82bf-55ec99c475a6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFILE_END_OF_FILE_INFORMATION, FILE_END_OF_FILE_INFORMATION, FILE_END_OF_FILE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_END_OF_FILE_INFORMATION, PFILE_END_OF_FILE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_END_OF_FILE_INFORMATION, kernel.file_end_of_file_information, kstruct_b_6c41bbd0-64be-4765-b79c-09e2dd86fa6f.xml, ntddk/FILE_END_OF_FILE_INFORMATION, ntddk/PFILE_END_OF_FILE_INFORMATION"
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
-	FILE_END_OF_FILE_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_END_OF_FILE_INFORMATION, *PFILE_END_OF_FILE_INFORMATION
---

# _FILE_END_OF_FILE_INFORMATION structure


## -description


The <b>FILE_END_OF_FILE_INFORMATION</b> structure is used as an argument to the <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> routine.


## -syntax


````
typedef struct _FILE_END_OF_FILE_INFORMATION {
  LARGE_INTEGER EndOfFile;
} FILE_END_OF_FILE_INFORMATION, *PFILE_END_OF_FILE_INFORMATION;
````


## -struct-fields




### -field EndOfFile

The absolute new end of file position as a byte offset from the start of the file. 


## -remarks



<b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file: that is, it is the offset to the byte immediately following the last valid byte in the file. 




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_END_OF_FILE_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

