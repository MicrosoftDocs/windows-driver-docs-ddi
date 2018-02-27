---
UID: NS:ntifs._FILE_GET_EA_INFORMATION
title: "_FILE_GET_EA_INFORMATION"
author: windows-driver-content
description: The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information.
old-location: ifsk\file_get_ea_information.htm
old-project: ifsk
ms.assetid: 2abaf505-b890-43b6-a277-d930417bdcb8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_GET_EA_INFORMATION, FILE_GET_EA_INFORMATION, FILE_GET_EA_INFORMATION structure [Installable File System Drivers], PFILE_GET_EA_INFORMATION, PFILE_GET_EA_INFORMATION structure pointer [Installable File System Drivers], _FILE_GET_EA_INFORMATION, fileinformationstructures_42834ee3-151e-4844-bd66-a20775e364b4.xml, ifsk.file_get_ea_information, ntifs/FILE_GET_EA_INFORMATION, ntifs/PFILE_GET_EA_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
-	ntifs.h
api_name:
-	FILE_GET_EA_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_GET_EA_INFORMATION, *PFILE_GET_EA_INFORMATION
---

# _FILE_GET_EA_INFORMATION structure


## -description


The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information. 


## -syntax


````
typedef struct _FILE_GET_EA_INFORMATION {
  ULONG NextEntryOffset;
  UCHAR EaNameLength;
  CHAR  EaName[1];
} FILE_GET_EA_INFORMATION, *PFILE_GET_EA_INFORMATION;
````


## -struct-fields




### -field NextEntryOffset

Offset, in bytes, of the next FILE_GET_EA_INFORMATION-typed entry. This member is zero if no other entries follow this one. 


### -field EaNameLength

Length, in bytes, of the <b>EaName</b> array. This value does not include a NULL terminator. 


### -field EaName

Specifies the first character of the name of the extended attribute to be queried. This is followed in memory by the remainder of the string. 


## -remarks



The FILE_GET_EA_INFORMATION structure is used to query for extended-attribute (EA) information. The EA information is returned in a <a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>-structured buffer. 

This structure must be aligned on a LONG (4-byte) boundary. 




## -see-also

<a href="..\ntifs\nf-ntifs-iocheckeabuffervalidity.md">IoCheckEaBufferValidity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549279">IRP_MJ_QUERY_EA</a>



<a href="..\wdm\ns-wdm-_file_full_ea_information.md">FILE_FULL_EA_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_GET_EA_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

