---
UID: NF:ntifs.IoGetRequestorSessionId
title: IoGetRequestorSessionId function (ntifs.h)
description: The IoGetRequestorSessionId routine returns the session ID for the process that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorsessionid.htm
tech.root: ifsk
ms.date: 08/26/2021
keywords: ["IoGetRequestorSessionId function"]
ms.keywords: IoGetRequestorSessionId, IoGetRequestorSessionId routine [Installable File System Drivers], ifsk.iogetrequestorsessionid, ioref_fe60ee3b-1b5b-4d9c-a4f2-456e05575349.xml, ntifs/IoGetRequestorSessionId
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetRequestorSessionId
 - ntifs/IoGetRequestorSessionId
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetRequestorSessionId
---

# IoGetRequestorSessionId function

## -description

The **IoGetRequestorSessionId** routine returns the session ID for the process that originally requested a given I/O operation.

## -parameters

### -param Irp [in]

A pointer to the I/O request packet (IRP) for the I/O operation.

### -param pSessionId [out]

A pointer to a caller-allocated variable that receives the session ID for the process that requested the I/O operation. If the call fails (STATUS_UNSUCCESSFUL), this parameter is set to -1.

## -returns

**IoGetRequestorSessionId** returns STATUS_SUCCESS if the session ID is successfully returned, and returns STATUS_UNSUCCESSFUL otherwise. STATUS_UNSUCCESSFUL is an error NTSTATUS value.

## -see-also

[**IoGetRequestorProcess**](nf-ntifs-iogetrequestorprocess.md)
