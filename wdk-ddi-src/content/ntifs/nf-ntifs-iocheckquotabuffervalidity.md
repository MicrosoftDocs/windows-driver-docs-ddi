---
UID: NF:ntifs.IoCheckQuotaBufferValidity
title: IoCheckQuotaBufferValidity function (ntifs.h)
description: Learn more about the IoCheckQuotaBufferValidity function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoCheckQuotaBufferValidity function"]
ms.keywords: IoCheckQuotaBufferValidity, IoCheckQuotaBufferValidity routine [Installable File System Drivers], ifsk.iocheckquotabuffervalidity, ioref_b4dc2b93-aaf1-450b-8240-b92792182057.xml, ntifs/IoCheckQuotaBufferValidity
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
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

The **IoCheckQuotaBufferValidity** routine checks whether the specified quota buffer is valid.

## -parameters

### -param QuotaBuffer [in]

Pointer to the buffer containing the quota entries to be checked.

### -param QuotaLength [in]

Length, in bytes, of **QuotaBuffer**.

### -param ErrorOffset [out]

A variable to receive the offset of the offending entry in the quota buffer if an error is found. This variable is only valid if an error occurs.

## -returns

**IoCheckQuotaBufferValidity** returns STATUS_SUCCESS if the quota buffer is valid. Otherwise, it returns STATUS_DATATYPE_MISALIGNMENT if the quota buffer is not ULONG-aligned. For all other errors, including misalignment of entries in the buffer, **IoCheckQuotaBufferValidity** returns STATUS_QUOTA_LIST_INCONSISTENT.

## -remarks

**IoCheckQuotaBufferValidity** checks each FILE_QUOTA_INFORMATION entry in the specified quota buffer to ensure that the following conditions are met:

* The entire entry must fall within the buffer.

* The value of **Sid** must be a security identifier (SID).

* The value of **SidLength** must match the length in bytes of the value of **Sid**.

* For all entries except the last, the value of **NextEntryOffset** must be greater than zero and must fall on a ULONG boundary.

In addition, **IoCheckQuotaBufferValidity** checks the quota buffer to ensure that the following conditions are met:

* The buffer must be ULONG-aligned.

* The length passed in **QuotaLength** matches the actual length of the buffer.

* The actual buffer length is nonnegative.

To be valid, the quota buffer must meet all of these conditions.

## -see-also

[**FILE_QUOTA_INFORMATION**](ns-ntifs-_file_quota_information.md)

[**IRP_MJ_QUERY_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-query-quota)

[**IRP_MJ_SET_QUOTA**](/windows-hardware/drivers/ifs/irp-mj-set-quota)
