---
UID: NS:ntifs._FILE_ACCESS_INFORMATION
title: "_FILE_ACCESS_INFORMATION"
author: windows-driver-content
description: The FILE_ACCESS_INFORMATION structure is used to query for or set the access rights of a file.
old-location: kernel\file_access_information.htm
old-project: kernel
ms.assetid: f5a09843-caf7-4550-bbc6-c0d799d66cd6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PFILE_ACCESS_INFORMATION, ,, A, C, E, F, FILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION structure [Kernel-Mode Driver Architecture], I, L, M, N, O, P, PFILE_ACCESS_INFORMATION, PFILE_ACCESS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, S, T, _, _FILE_ACCESS_INFORMATION, kernel.file_access_information, kstruct_b_3419b751-aa57-41e2-a51d-35bb5a6f38c8.xml, ntifs/FILE_ACCESS_INFORMATION, ntifs/PFILE_ACCESS_INFORMATION"
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
-	FILE_ACCESS_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION
---

# _FILE_ACCESS_INFORMATION structure


## -description


The <b>FILE_ACCESS_INFORMATION</b> structure is used to query for or set the access rights of a file.


## -syntax


````
typedef struct _FILE_ACCESS_INFORMATION {
  ACCESS_MASK AccessFlags;
} FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION;
````


## -struct-fields




### -field AccessFlags

Flags that specify a set of access rights in the access mask of an access control entry. This member is a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.


## -remarks



This structure is used by the <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> routine.

The <i>AccessFlags</i> parameter is an access mask that encodes the user rights to a file object. An access mask can be used to encode the rights to an object that is assigned to a user or a user group, or to encode the requested access when a user opens an object. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_ACCESS_INFORMATION structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

