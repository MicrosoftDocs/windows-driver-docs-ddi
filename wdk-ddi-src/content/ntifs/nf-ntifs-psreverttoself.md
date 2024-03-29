---
UID: NF:ntifs.PsRevertToSelf
title: PsRevertToSelf function (ntifs.h)
description: The PsRevertToSelf routine ends the calling thread's impersonation of a client.
old-location: ifsk\psreverttoself.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PsRevertToSelf function"]
ms.keywords: PsRevertToSelf, PsRevertToSelf routine [Installable File System Drivers], ifsk.psreverttoself, ntifs/PsRevertToSelf, psref_da555465-d8ee-4ae6-af44-cf0af7633458.xml
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PsRevertToSelf
 - ntifs/PsRevertToSelf
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsRevertToSelf
---

# PsRevertToSelf function


## -description

The <b>PsRevertToSelf</b> routine ends the calling thread's impersonation of a client.

## -remarks

A server thread can impersonate a client by calling the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psimpersonateclient">PsImpersonateClient</a> routine. When the thread is done impersonating the client, it can call the <b>PsRevertToSelf</b> routine to end all impersonations.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psimpersonateclient">PsImpersonateClient</a>
