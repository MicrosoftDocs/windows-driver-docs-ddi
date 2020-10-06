---
UID: NF:ntifs.IoCheckQuotaBufferValidity
title: IoCheckQuotaBufferValidity function (ntifs.h)
description: The IoCheckQuotaBufferValidity routine checks whether the specified quota buffer is valid.
old-location: ifsk\iocheckquotabuffervalidity.htm
tech.root: ifsk
ms.assetid: 8a003d78-3b7d-44af-a7cf-a2a516c2cc20
ms.date: 04/16/2018
keywords: ["IoCheckQuotaBufferValidity function"]
ms.keywords: IoCheckQuotaBufferValidity, IoCheckQuotaBufferValidity routine [Installable File System Drivers], ifsk.iocheckquotabuffervalidity, ioref_b4dc2b93-aaf1-450b-8240-b92792182057.xml, ntifs/IoCheckQuotaBufferValidity
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCheckQuotaBufferValidity
 - ntifs/IoCheckQuotaBufferValidity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCheckQuotaBufferValidity
---

# IoCheckQuotaBufferValidity function


## -description

The <b>IoCheckQuotaBufferValidity</b> routine checks whether the specified quota buffer is valid.

## -parameters

### -param QuotaBuffer 

[in]
Pointer to the buffer containing the quota entries to be checked.

### -param QuotaLength 

[in]
Length, in bytes, of <i>QuotaBuffer</i>.

### -param ErrorOffset 

[out]
A variable to receive the offset of the offending entry in the quota buffer if an error is found. This variable is only valid if an error occurs.

## -returns

<b>IoCheckQuotaBufferValidity</b> returns STATUS_SUCCESS if the quota buffer is valid. Otherwise, it returns STATUS_DATATYPE_MISALIGNMENT if the quota buffer is not ULONG-aligned. For all other errors, including misalignment of entries in the buffer, <b>IoCheckQuotaBufferValidity</b> returns STATUS_QUOTA_LIST_INCONSISTENT.

## -remarks

<b>IoCheckQuotaBufferValidity</b> checks each FILE_QUOTA_INFORMATION entry in the specified quota buffer to ensure that the following conditions are met:

<ul>
<li>
The entire entry must fall within the buffer.

</li>
<li>
The value of <b>Sid</b> must be a security identifier (SID).

</li>
<li>
The value of <b>SidLength</b> must match the length in bytes of the value of <b>Sid</b>.

</li>
<li>
For all entries except the last, the value of <b>NextEntryOffset</b> must be greater than zero and must fall on a ULONG boundary.

</li>
</ul>
In addition, <b>IoCheckQuotaBufferValidity</b> checks the quota buffer to ensure that the following conditions are met:

<ul>
<li>
The buffer must be ULONG-aligned.

</li>
<li>
The length passed in <i>QuotaLength</i> matches the actual length of the buffer.

</li>
<li>
The actual buffer length is nonnegative.

</li>
</ul>
To be valid, the quota buffer must meet all of these conditions.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_quota_information">FILE_QUOTA_INFORMATION</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-query-quota">IRP_MJ_QUERY_QUOTA</a>



<a href="/windows-hardware/drivers/ifs/irp-mj-set-quota">IRP_MJ_SET_QUOTA</a>