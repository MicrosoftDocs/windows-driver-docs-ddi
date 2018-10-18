---
UID: NS:ntifs._FILE_ACCESS_INFORMATION
title: "_FILE_ACCESS_INFORMATION"
author: windows-driver-content
description: The FILE_ACCESS_INFORMATION structure is used to query for or set the access rights of a file.
old-location: kernel\file_access_information.htm
tech.root: kernel
ms.assetid: f5a09843-caf7-4550-bbc6-c0d799d66cd6
ms.date: 4/30/2018
ms.keywords: "*PFILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ACCESS_INFORMATION, PFILE_ACCESS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ACCESS_INFORMATION, kernel.file_access_information, kstruct_b_3419b751-aa57-41e2-a51d-35bb5a6f38c8.xml, ntifs/FILE_ACCESS_INFORMATION, ntifs/PFILE_ACCESS_INFORMATION"
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
-	FILE_ACCESS_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION
---

# _FILE_ACCESS_INFORMATION structure


## -description


The <b>FILE_ACCESS_INFORMATION</b> structure is used to query for or set the access rights of a file.


## -struct-fields




### -field AccessFlags

Flags that specify a set of access rights in the access mask of an access control entry. This member is a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a> routine.

The <i>AccessFlags</i> parameter is an access mask that encodes the user rights to a file object. An access mask can be used to encode the rights to an object that is assigned to a user or a user group, or to encode the requested access when a user opens an object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
 

 

