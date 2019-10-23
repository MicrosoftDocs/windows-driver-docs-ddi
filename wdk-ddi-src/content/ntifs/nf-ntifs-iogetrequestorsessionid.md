---
UID: NF:ntifs.IoGetRequestorSessionId
title: IoGetRequestorSessionId function (ntifs.h)
description: The IoGetRequestorSessionId routine returns the session ID for the process that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorsessionid.htm
tech.root: ifsk
ms.assetid: 9e13cf62-d71e-4878-becd-d34beb2f59b3
ms.date: 04/16/2018
ms.keywords: IoGetRequestorSessionId, IoGetRequestorSessionId routine [Installable File System Drivers], ifsk.iogetrequestorsessionid, ioref_fe60ee3b-1b5b-4d9c-a4f2-456e05575349.xml, ntifs/IoGetRequestorSessionId
ms.topic: function
f1_keywords:
 - "ntifs/IoGetRequestorSessionId"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetRequestorSessionId
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetRequestorSessionId function


## -description


The <b>IoGetRequestorSessionId</b> routine returns the session ID for the process that originally requested a given I/O operation.


## -parameters




### -param Irp [in]

A pointer to the I/O request packet (IRP) for the I/O operation. 


### -param pSessionId [out]

A pointer to a caller-allocated variable that receives the session ID for the process that requested the I/O operation. If the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocessid">IoGetRequestorProcessId</a> fails, this variable is set to -1.


## -returns




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocessid">IoGetRequestorProcessId</a> returns STATUS_SUCCESS if the session ID is successfully returned, STATUS_UNSUCCESSFUL otherwise. STATUS_UNSUCCESSFUL is an error NTSTATUS value. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocess">IoGetRequestorProcess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogetrequestorprocessid">IoGetRequestorProcessId</a>
 

 

