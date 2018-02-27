---
UID: NS:wdm._FILE_POSITION_INFORMATION
title: "_FILE_POSITION_INFORMATION"
author: windows-driver-content
description: The FILE_POSITION_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_position_information.htm
old-project: kernel
ms.assetid: 04f01faf-599e-4c62-82ce-c147b4820c8f
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFILE_POSITION_INFORMATION, FILE_POSITION_INFORMATION, FILE_POSITION_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_POSITION_INFORMATION, PFILE_POSITION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_POSITION_INFORMATION, kernel.file_position_information, kstruct_b_5edd5ea9-9229-4764-86aa-24054a1ec9b9.xml, wdm/FILE_POSITION_INFORMATION, wdm/PFILE_POSITION_INFORMATION"
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
-	Wdm.h
apiname:
-	FILE_POSITION_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_POSITION_INFORMATION, *PFILE_POSITION_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_POSITION_INFORMATION structure


## -description


The <b>FILE_POSITION_INFORMATION</b> structure is used as an argument to routines that query or set file information.


## -syntax


````
typedef struct _FILE_POSITION_INFORMATION {
  LARGE_INTEGER CurrentByteOffset;
} FILE_POSITION_INFORMATION, *PFILE_POSITION_INFORMATION;
````


## -struct-fields




### -field CurrentByteOffset

The byte offset of the current file pointer.


## -remarks



FILE_READ_DATA or FILE_WRITE_DATA access to the file is required to change this information about the file, and the file must be opened for synchronous I/O.

If the file was opened or created with the FILE_NO_INTERMEDIATE_BUFFERING option, the value of <b>CurrentByteOffset</b> must be an integral multiple of the sector size of the underlying device.




## -see-also

<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_POSITION_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

