---
UID: NF:ntifs.IoCheckEaBufferValidity
title: IoCheckEaBufferValidity function (ntifs.h)
description: Learn more about the IoCheckEaBufferValidity function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["IoCheckEaBufferValidity function"]
ms.keywords: IoCheckEaBufferValidity, IoCheckEaBufferValidity function [Installable File System Drivers], ifsk.iocheckeabuffervalidity, ioref_cda82410-a6a9-40df-83ac-c1376a129a7a.xml, ntifs/IoCheckEaBufferValidity
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCheckEaBufferValidity
 - ntifs/IoCheckEaBufferValidity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoCheckEaBufferValidity
---

# IoCheckEaBufferValidity function

## -description

The **IoCheckEaBufferValidity** routine checks whether the specified extended attribute (EA) buffer is valid.

## -parameters

### -param EaBuffer [in]

Pointer to the buffer containing the EAs to be checked.

### -param EaLength [in]

Length, in bytes, of **EaBuffer**.

### -param ErrorOffset [out]

Pointer to a variable that receives the offset of the offending entry in the EA buffer if an error is found. This variable is only valid if an error occurs.

## -returns

**IoCheckEaBufferValidity** returns STATUS_SUCCESS if the EA buffer is valid; otherwise it returns STATUS_EA_LIST_INCONSISTENT.

## -remarks

**IoCheckEaBufferValidity** checks each FILE_FULL_EA_INFORMATION entry in the specified EA buffer to ensure that the following conditions are met:

* The entire entry must fall within the buffer.

* The value of **EaName** must be a null-terminated character array.

* The value of **EaNameLength** must match the length in bytes of the **EaName** array (not including the zero-terminator).

* For all entries except the last, the value of **NextEntryOffset** must be greater than zero and must fall on a ULONG boundary.

In addition, **IoCheckEaBufferValidity** checks the EA buffer to ensure that the following conditions are met:

* The length passed in **EaLength** matches the actual length of the buffer.

* The actual buffer length is nonnegative.

To be valid, the EA buffer must meet all of these conditions.

**IoCheckEaBufferValidity** doesn't perform any synchronization to ensure that the contents of **EaBuffer** do not change asynchronously. If a user-mode application can access the buffer in another thread, the application could change the buffer while **IoCheckEaBufferValidity** is running. This change might cause the routine to return incorrect information.  To avoid this scenario, the driver should copy the buffer before calling **IoCheckEaBufferValidity**.  After the buffer has been validated, the caller should use only the validated copy, not the original buffer.

## -see-also

[**FILE_FULL_EA_INFORMATION**](../wdm/ns-wdm-_file_full_ea_information.md)

[**IRP_MJ_QUERY_EA**](/windows-hardware/drivers/ifs/irp-mj-query-ea)

[**IRP_MJ_SET_EA**](/windows-hardware/drivers/ifs/irp-mj-set-ea)
