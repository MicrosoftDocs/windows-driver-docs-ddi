---
UID: NF:wdm.IoGetCurrentProcess
title: IoGetCurrentProcess function (wdm.h)
description: The IoGetCurrentProcess routine returns a pointer to the current process.
old-location: kernel\iogetcurrentprocess.htm
tech.root: kernel
ms.assetid: 97a5c14f-949a-4455-9109-79355e5dec37
ms.date: 04/30/2018
ms.keywords: IoGetCurrentProcess, IoGetCurrentProcess routine [Kernel-Mode Driver Architecture], k104_f59c640e-e335-46e0-a6ca-2f672bb6fc35.xml, kernel.iogetcurrentprocess, wdm/IoGetCurrentProcess, PsGetCurrentProcess
ms.topic: function
f1_keywords:
 - "wdm/IoGetCurrentProcess"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- IoGetCurrentProcess
- PsGetCurrentProcess
product:
- Windows
targetos: Windows
req.typenames: 
---

# IoGetCurrentProcess function

## -description

The **IoGetCurrentProcess** routine returns a pointer to the current process. Call **PsGetCurrentProcess** instead of **IoGetCurrentProcess**.

## -returns

**IoGetCurrentProcess** returns a pointer to the current process.

## -remarks

This routine is identical to **PsGetCurrentProcess**.

``#define PsGetCurrentProcess IoGetCurrentProcess``

## -see-also

[PsGetCurrentThread](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psgetcurrentthread)
