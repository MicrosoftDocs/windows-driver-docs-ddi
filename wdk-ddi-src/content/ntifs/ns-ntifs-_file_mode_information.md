---
UID: NS:ntifs._FILE_MODE_INFORMATION
title: "_FILE_MODE_INFORMATION"
author: windows-driver-content
description: The FILE_MODE_INFORMATION structure is used to query or set the access mode of a file.
old-location: kernel\file_mode_information.htm
old-project: kernel
ms.assetid: c01ee792-4e39-4135-b389-a5c5ac832245
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFILE_MODE_INFORMATION, FILE_MODE_INFORMATION, FILE_MODE_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_MODE_INFORMATION, PFILE_MODE_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_MODE_INFORMATION, kernel.file_mode_information, kstruct_b_ab9ae7a9-242c-4f0e-a44f-8c5883b0c3ce.xml, ntifs/FILE_MODE_INFORMATION, ntifs/PFILE_MODE_INFORMATION"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntifs.h
api_name:
-	FILE_MODE_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_MODE_INFORMATION, *PFILE_MODE_INFORMATION
---

# _FILE_MODE_INFORMATION structure


## -description


The <b>FILE_MODE_INFORMATION</b> structure is used to query or set the access mode of a file.


## -syntax


````
typedef struct _FILE_MODE_INFORMATION {
  ULONG Mode;
} FILE_MODE_INFORMATION, *PFILE_MODE_INFORMATION;
````


## -struct-fields




### -field Mode

Specifies the mode in which the file will be accessed following a create-file or open-file operation. This parameter is either zero or the bitwise OR of one or more of the following file option flags:





#### FILE_WRITE_THROUGH

Any system services, file system drivers (FSDs), and drivers that write data to the file must actually transfer the data into the file before any requested write operation is considered complete.



#### FILE_SEQUENTIAL_ONLY

All accesses to the file will be sequential.



#### FILE_NO_INTERMEDIATE_BUFFERING

The file cannot be cached or buffered in a driver's internal buffers.



#### FILE_SYNCHRONOUS_IO_ALERT

All operations on the file are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. This flag also causes the I/O system to maintain the file position context.



#### FILE_SYNCHRONOUS_IO_NONALERT

All operations on the file are performed synchronously. Wait requests in the system that must synchronize I/O queuing and completion are not subject to alerts. This flag also causes the I/O system to maintain the file position context.



#### FILE_DELETE_ON_CLOSE

Delete the file when the last handle to the file is closed.

These flags are defined in the Wdm.h header file. For more information, see the Remarks section.


## -remarks



This structure contains a set of flags that specify the mode in which the file can be accessed. These flags are a subset of the options that can be specified in the <i>CreateOptions</i> parameter of the <a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a> routine.

This structure is used by the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> routine.




## -see-also

<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>



<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_MODE_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

