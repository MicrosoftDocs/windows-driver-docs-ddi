---
UID: NF:ntifs.PoDeletePowerRequest
title: PoDeletePowerRequest function (ntifs.h)
description: Learn more about the PoDeletePowerRequest routine.
tech.root: kernel
ms.date: 07/06/2023
keywords: ["PoDeletePowerRequest function"]
ms.keywords: PoDeletePowerRequest, PoDeletePowerRequest routine [Kernel-Mode Driver Architecture], kernel.podeletepowerrequest, portn_a0e21464-039d-4619-b9d5-f67bf2d7273b.xml, wdm/PoDeletePowerRequest
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 7
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
req.irql: <=APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoDeletePowerRequest
 - ntifs/PoDeletePowerRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoDeletePowerRequest
---

# PoDeletePowerRequest function (ntifs.h)

## -description

The **PoDeletePowerRequest** routine deletes a power request object.

## -parameters

### -param PowerRequest [in, out]

A pointer to a power request object that was created by the [**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md) routine.

## -remarks

The driver must delete the power request object before it deletes the device object that was used to create the power request object.

## -see-also

[**PoCreatePowerRequest**](nf-ntifs-pocreatepowerrequest.md)
