---
UID: NF:ntddk.PsGetServerSiloActiveConsoleId
title: PsGetServerSiloActiveConsoleId function (ntddk.h)
description: Gets the active console for the current server silo context for the supplied thread.
old-location: kernel\psgetserversiloactiveconsoleid.htm
tech.root: kernel
ms.assetid: 66b3c35d-681c-464a-86fa-972825bf3e97
ms.date: 04/30/2018
keywords: ["PsGetServerSiloActiveConsoleId function"]
ms.keywords: PsGetServerSiloActiveConsoleId, PsGetServerSiloActiveConsoleId method [Kernel-Mode Driver Architecture], kernel.psgetserversiloactiveconsoleid, ntddk/PsGetServerSiloActiveConsoleId
f1_keywords:
 - "ntddk/PsGetServerSiloActiveConsoleId"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PsGetServerSiloActiveConsoleId
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsGetServerSiloActiveConsoleId function


## -description


Gets the active console for the current server silo context
    for the supplied thread.
			
            


## -parameters




### -param Silo

A pointer to the silo of the job. 


## -returns



Returns the session id for the active console session.



