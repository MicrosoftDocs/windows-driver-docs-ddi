---
UID: NS:wdm._FILE_STANDARD_INFORMATION
title: "_FILE_STANDARD_INFORMATION"
author: windows-driver-content
description: The FILE_STANDARD_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_standard_information.htm
old-project: kernel
ms.assetid: 9ff7efec-4844-4abf-89c2-472afc959697
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kstruct_b_86abcab8-11e5-45de-983a-e78c6cb40a93.xml, wdm/PFILE_STANDARD_INFORMATION, FILE_STANDARD_INFORMATION, PFILE_STANDARD_INFORMATION, _FILE_STANDARD_INFORMATION, wdm/FILE_STANDARD_INFORMATION, *PFILE_STANDARD_INFORMATION, kernel.file_standard_information, PFILE_STANDARD_INFORMATION structure pointer [Kernel-Mode Driver Architecture], FILE_STANDARD_INFORMATION structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	FILE_STANDARD_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PFILE_STANDARD_INFORMATION, FILE_STANDARD_INFORMATION"
req.product: Windows 10 or later.
---

# _FILE_STANDARD_INFORMATION structure


## -description


The <b>FILE_STANDARD_INFORMATION</b> structure is used as an argument to routines that query or set file information.


## -syntax


````
typedef struct _FILE_STANDARD_INFORMATION {
  LARGE_INTEGER AllocationSize;
  LARGE_INTEGER EndOfFile;
  ULONG         NumberOfLinks;
  BOOLEAN       DeletePending;
  BOOLEAN       Directory;
} FILE_STANDARD_INFORMATION, *PFILE_STANDARD_INFORMATION;
````


## -struct-fields




### -field AllocationSize

The file allocation size in bytes. Usually, this value is a multiple of the sector or cluster size of the underlying physical device. 


### -field EndOfFile

The end of file location as a byte offset.


### -field NumberOfLinks

The number of hard links to the file.


### -field DeletePending

The delete pending status. <b>TRUE</b> indicates that a file deletion has been requested.


### -field Directory

The file directory status. <b>TRUE</b> indicates the file object represents a directory. 


## -remarks



<b>EndOfFile</b> specifies the byte offset to the end of the file. Because this value is zero-based, it actually refers to the first free byte in the file; that is, it is the offset to the byte immediately following the last valid byte in the file. 




## -see-also

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_STANDARD_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

