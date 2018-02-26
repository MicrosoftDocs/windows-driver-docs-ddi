---
UID: NS:ntddk._FILE_DISPOSITION_INFORMATION
title: "_FILE_DISPOSITION_INFORMATION"
author: windows-driver-content
description: The FILE_DISPOSITION_INFORMATION structure is used as an argument to the ZwSetInformationFile routine.
old-location: kernel\file_disposition_information.htm
old-project: kernel
ms.assetid: a13b5411-a0dd-4a54-98a8-419e2f0e95b8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PFILE_DISPOSITION_INFORMATION, ,, A, D, E, F, FILE_DISPOSITION_INFORMATION, FILE_DISPOSITION_INFORMATION structure [Kernel-Mode Driver Architecture], I, L, M, N, O, P, PFILE_DISPOSITION_INFORMATION, PFILE_DISPOSITION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, S, T, _, _FILE_DISPOSITION_INFORMATION, kernel.file_disposition_information, kstruct_b_3796aa61-042a-435d-bfa9-c77c6a0dff98.xml, ntddk/FILE_DISPOSITION_INFORMATION, ntddk/PFILE_DISPOSITION_INFORMATION"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	FILE_DISPOSITION_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_DISPOSITION_INFORMATION, *PFILE_DISPOSITION_INFORMATION
---

# _FILE_DISPOSITION_INFORMATION structure


## -description


The <b>FILE_DISPOSITION_INFORMATION</b> structure is used as an argument to the <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a> routine.


## -syntax


````
typedef struct _FILE_DISPOSITION_INFORMATION {
  BOOLEAN DeleteFile;
} FILE_DISPOSITION_INFORMATION, *PFILE_DISPOSITION_INFORMATION;
````


## -struct-fields




### -field DeleteFile

Indicates whether the operating system file should delete the file when the file is closed. Set this member to <b>TRUE</b> to delete the file when it is closed. Otherwise, set to <b>FALSE</b>. Setting this member to <b>FALSE</b> has no effect if the handle was opened with FILE_FLAG_DELETE_ON_CLOSE.


## -remarks



The caller must have DELETE access to a given file in order to call <b>ZwSetInformationFile</b> with <b>DeleteFile</b> set to <b>TRUE</b> in this structure. Subsequently, the only legal operation by such a caller is to close the open file handle. 

A file marked for deletion is not actually deleted until all open handles for the file object have been closed and the link count for the file is zero.




## -see-also

<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_DISPOSITION_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

