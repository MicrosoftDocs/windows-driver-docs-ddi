---
UID: NF:wdm.IoWithinStackLimits
title: IoWithinStackLimits function (wdm.h)
description: The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread.
tech.root: kernel
ms.date: 12/12/2022
keywords: ["IoWithinStackLimits function"]
ms.keywords: IoWithinStackLimits, IoWithinStackLimits routine [Kernel-Mode Driver Architecture], k104_631648cb-6ba2-47b1-8745-e6314e17be30.xml, kernel.iowithinstacklimits, wdm/IoWithinStackLimits
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: IRQL <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoWithinStackLimits
 - wdm/IoWithinStackLimits
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoWithinStackLimits
---

## -description

The **IoWithinStackLimits** routine determines whether a region of memory is within the stack limit of the current thread.

## -parameters

### -param RegionStart [in]

A pointer to the start of the region.

### -param RegionSize [in]

The size of the region.

## -returns

**IoWithinStackLimits** returns **TRUE** is the current thread's stack contains the region completely and **FALSE** otherwise.

## -remarks

The **IoWithinStackLimits** routine considers all possible stack segments and the DPC stack, if necessary.

For drivers that use [KeExpandKernelStackAndCallout](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout), **IoWithinStackLimits** considers only the current thread.

## -see-also

[IoGetInitialStack](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetinitialstack)

[IoGetRemainingStackSize](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetremainingstacksize)

[IoGetStackLimits](/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetstacklimits)
