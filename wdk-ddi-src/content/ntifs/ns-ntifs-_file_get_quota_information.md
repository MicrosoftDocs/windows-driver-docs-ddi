---
UID: NS:ntifs._FILE_GET_QUOTA_INFORMATION
title: _FILE_GET_QUOTA_INFORMATION (ntifs.h)
description: The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information.
old-location: ifsk\file_get_quota_information.htm
tech.root: ifsk
ms.assetid: 4c4d57bd-28b3-4db3-a172-bc1a27dd10b2
ms.date: 04/16/2018
keywords: ["FILE_GET_QUOTA_INFORMATION structure"]
ms.keywords: "*PFILE_GET_QUOTA_INFORMATION, FILE_GET_QUOTA_INFORMATION, FILE_GET_QUOTA_INFORMATION structure [Installable File System Drivers], PFILE_GET_QUOTA_INFORMATION, PFILE_GET_QUOTA_INFORMATION structure pointer [Installable File System Drivers], _FILE_GET_QUOTA_INFORMATION, fileinformationstructures_e64ee968-bf98-422e-9bed-837b984fbc33.xml, ifsk.file_get_quota_information, ntifs/FILE_GET_QUOTA_INFORMATION, ntifs/PFILE_GET_QUOTA_INFORMATION"
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
req.typenames: FILE_GET_QUOTA_INFORMATION, *PFILE_GET_QUOTA_INFORMATION
f1_keywords:
 - _FILE_GET_QUOTA_INFORMATION
 - ntifs/_FILE_GET_QUOTA_INFORMATION
 - PFILE_GET_QUOTA_INFORMATION
 - ntifs/PFILE_GET_QUOTA_INFORMATION
 - FILE_GET_QUOTA_INFORMATION
 - ntifs/FILE_GET_QUOTA_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_GET_QUOTA_INFORMATION
---

# _FILE_GET_QUOTA_INFORMATION structure


## -description

The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information.

## -struct-fields

### -field NextEntryOffset

Offset, in bytes, of the next FILE_GET_QUOTA_INFORMATION-typed entry. This member is zero if no other entries follow this one.

### -field SidLength

Length, in bytes, of the <b>Sid</b> member.

### -field Sid

Security identifier (<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>) whose quota information is to be returned.

## -remarks

The FILE_GET_QUOTA_INFORMATION structure is used to query for quota information. The quota information is returned in a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a>-structured buffer. 

This structure must be aligned on a LONG (4-byte) boundary.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iocheckquotabuffervalidity">IoCheckQuotaBufferValidity</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>