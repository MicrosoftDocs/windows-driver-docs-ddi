---
UID: NF:wdm.IoWithinStackLimits
title: IoWithinStackLimits function (wdm.h)
description: The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread.
old-location: kernel\iowithinstacklimits.htm
tech.root: kernel
ms.assetid: af182cd5-23b5-4d5b-b3d4-ec65ec087d0b
ms.date: 04/30/2018
keywords: ["IoWithinStackLimits function"]
ms.keywords: IoWithinStackLimits, IoWithinStackLimits routine [Kernel-Mode Driver Architecture], k104_631648cb-6ba2-47b1-8745-e6314e17be30.xml, kernel.iowithinstacklimits, wdm/IoWithinStackLimits
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
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

# IoWithinStackLimits function


## -description

The <b>IoWithinStackLimits</b> routine determines whether a region of memory is within the stack limit of the current thread.

## -parameters

### -param RegionStart 

[in]
A pointer to the start of the region.

### -param RegionSize 

[in]
The size of the region.

## -returns

<b>IoWithinStackLimits</b> returns <b>TRUE</b> is the current thread's stack contains the region completely and <b>FALSE</b> otherwise.

## -remarks

The <b>IoWithinStackLimits</b> routine considers all possible stack segments and the DPC stack, if necessary.

<div class="alert"><b>Note</b>    For drivers that use <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keexpandkernelstackandcallout">KeExpandKernelStackAndCallout</a>, <b>IoWithinStackLimits</b> considers only the current thread.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetinitialstack">IoGetInitialStack</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetremainingstacksize">IoGetRemainingStackSize</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetstacklimits">IoGetStackLimits</a>