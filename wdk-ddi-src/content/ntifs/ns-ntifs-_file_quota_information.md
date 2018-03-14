---
UID: NS:ntifs._FILE_QUOTA_INFORMATION
title: "_FILE_QUOTA_INFORMATION"
author: windows-driver-content
description: The FILE_QUOTA_INFORMATION structure is used to query or set per-user quota information for each of the files in a directory.
old-location: ifsk\file_quota_information.htm
old-project: ifsk
ms.assetid: f5b17648-cd6e-4a6d-a00e-b4dfdcbcf0ea
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFILE_QUOTA_INFORMATION, FILE_QUOTA_INFORMATION, FILE_QUOTA_INFORMATION structure [Installable File System Drivers], PFILE_QUOTA_INFORMATION, PFILE_QUOTA_INFORMATION structure pointer [Installable File System Drivers], _FILE_QUOTA_INFORMATION, fileinformationstructures_38604040-0780-47f3-88b3-aef3e3eab993.xml, ifsk.file_quota_information, ntifs/FILE_QUOTA_INFORMATION, ntifs/PFILE_QUOTA_INFORMATION"
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
-	FILE_QUOTA_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_QUOTA_INFORMATION, *PFILE_QUOTA_INFORMATION
---

# _FILE_QUOTA_INFORMATION structure


## -description


The FILE_QUOTA_INFORMATION structure is used to query or set per-user quota information for each of the files in a directory. 


## -syntax


````
typedef struct _FILE_QUOTA_INFORMATION {
  ULONG         NextEntryOffset;
  ULONG         SidLength;
  LARGE_INTEGER ChangeTime;
  LARGE_INTEGER QuotaUsed;
  LARGE_INTEGER QuotaThreshold;
  LARGE_INTEGER QuotaLimit;
  SID           Sid;
} FILE_QUOTA_INFORMATION, *PFILE_QUOTA_INFORMATION;
````


## -struct-fields




### -field NextEntryOffset

Offset, in bytes, of the next quota entry in the list. If there are no more entries after the current one, this member is zero. 


### -field SidLength

Length, in bytes, of the <b>Sid</b> member. 


### -field ChangeTime

Time when this quota entry was last changed. 


### -field QuotaUsed

Amount of disk space on this volume that is currently being used by the user. 


### -field QuotaThreshold

Maximum mount of disk space on this volume that can be used by the user without triggering an event. For more information, see <a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>. 


### -field QuotaLimit

Maximum amount of disk space on this volume that can be used by the user. 


### -field Sid

Security identifier (SID) of the user. 


## -remarks



No specific access rights are required to query this information. To perform this query, create an IRP with major function code IRP_MJ_QUERY_QUOTA. 

FILE_WRITE_DATA access to the volume is required to set this information. To perform this operation, create an IRP with major function code IRP_MJ_SET_QUOTA. 

To check the validity of a buffer containing FILE_QUOTA_INFORMATION structure, call <a href="..\ntifs\nf-ntifs-iocheckquotabuffervalidity.md">IoCheckQuotaBufferValidity</a>. 

On 32-bit platforms, this structure must be aligned on a LONG (4-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on a 4-byte boundary. 

On 64-bit platforms, this structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549401">IRP_MJ_SET_QUOTA</a>



<a href="..\ntifs\ns-ntifs-_file_fs_control_information.md">FILE_FS_CONTROL_INFORMATION</a>



<a href="..\ntifs\nf-ntifs-iocheckquotabuffervalidity.md">IoCheckQuotaBufferValidity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549293">IRP_MJ_QUERY_QUOTA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FILE_QUOTA_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

