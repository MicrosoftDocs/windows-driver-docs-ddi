---
UID: NS:ntifs._FILE_QUOTA_INFORMATION
title: _FILE_QUOTA_INFORMATION (ntifs.h)
description: The FILE_QUOTA_INFORMATION structure is used to query or set per-user quota information for each of the files in a directory.
old-location: ifsk\file_quota_information.htm
tech.root: ifsk
ms.assetid: f5b17648-cd6e-4a6d-a00e-b4dfdcbcf0ea
ms.date: 04/16/2018
keywords: ["FILE_QUOTA_INFORMATION structure"]
ms.keywords: "*PFILE_QUOTA_INFORMATION, FILE_QUOTA_INFORMATION, FILE_QUOTA_INFORMATION structure [Installable File System Drivers], PFILE_QUOTA_INFORMATION, PFILE_QUOTA_INFORMATION structure pointer [Installable File System Drivers], _FILE_QUOTA_INFORMATION, fileinformationstructures_38604040-0780-47f3-88b3-aef3e3eab993.xml, ifsk.file_quota_information, ntifs/FILE_QUOTA_INFORMATION, ntifs/PFILE_QUOTA_INFORMATION"
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
targetos: Windows
req.typenames: FILE_QUOTA_INFORMATION, *PFILE_QUOTA_INFORMATION
f1_keywords:
 - _FILE_QUOTA_INFORMATION
 - ntifs/_FILE_QUOTA_INFORMATION
 - PFILE_QUOTA_INFORMATION
 - ntifs/PFILE_QUOTA_INFORMATION
 - FILE_QUOTA_INFORMATION
 - ntifs/FILE_QUOTA_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_QUOTA_INFORMATION
---

# _FILE_QUOTA_INFORMATION structure


## -description

The FILE_QUOTA_INFORMATION structure is used to query or set per-user quota information for each of the files in a directory.

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

Maximum mount of disk space on this volume that can be used by the user without triggering an event. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>.

### -field QuotaLimit

Maximum amount of disk space on this volume that can be used by the user.

### -field Sid

Security identifier (SID) of the user.

## -remarks

No specific access rights are required to query this information. To perform this query, create an IRP with major function code IRP_MJ_QUERY_QUOTA. 

FILE_WRITE_DATA access to the volume is required to set this information. To perform this operation, create an IRP with major function code IRP_MJ_SET_QUOTA. 

To check the validity of a buffer containing FILE_QUOTA_INFORMATION structure, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>. 

On 32-bit platforms, this structure must be aligned on a LONG (4-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on a 4-byte boundary. 

On 64-bit platforms, this structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry, except the last, falls on an 8-byte boundary.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>

