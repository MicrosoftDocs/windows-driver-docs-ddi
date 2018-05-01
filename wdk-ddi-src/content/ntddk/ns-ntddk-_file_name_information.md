---
UID: NS:ntddk._FILE_NAME_INFORMATION
title: "_FILE_NAME_INFORMATION"
author: windows-driver-content
description: The FILE_NAME_INFORMATION structure is used as argument to the ZwQueryInformationFile and ZwSetInformationFile routines.
old-location: kernel\file_name_information.htm
old-project: kernel
ms.assetid: 04ec8e82-d74d-4827-8533-aa57e3638a45
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: "*PFILE_NAME_INFORMATION, FILE_NAME_INFORMATION, FILE_NAME_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_NAME_INFORMATION, PFILE_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_NAME_INFORMATION, kernel.file_name_information, kstruct_b_075348cd-50d6-450f-9a9d-a5ad8fd985e3.xml, ntddk/FILE_NAME_INFORMATION, ntddk/PFILE_NAME_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
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
-	FILE_NAME_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_NAME_INFORMATION, *PFILE_NAME_INFORMATION
---

# _FILE_NAME_INFORMATION structure


## -description


The <b>FILE_NAME_INFORMATION</b> structure is used as argument to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> routines.


## -struct-fields




### -field FileNameLength

Specifies the length, in bytes, of the file name string.


### -field FileName

Specifies the first character of the file name string. This is followed in memory by the remainder of the string.


## -remarks



The <b>ZwQueryInformationFile</b> routine uses this structure to return the file name string to the caller. For more information about the form of the name returned, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>.

Callers of <a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a> can use this structure to specify a new short name for a file.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567096">ZwSetInformationFile</a>
 

 

