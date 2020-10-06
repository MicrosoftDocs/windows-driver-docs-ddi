---
UID: NF:wdm.IoFreeMdl
title: IoFreeMdl function (wdm.h)
description: The IoFreeMdl routine releases a caller-allocated memory descriptor list (MDL).
old-location: kernel\iofreemdl.htm
tech.root: kernel
ms.assetid: e984400a-b94f-4848-af56-79695b327404
ms.date: 04/30/2018
keywords: ["IoFreeMdl function"]
ms.keywords: IoFreeMdl, IoFreeMdl routine [Kernel-Mode Driver Architecture], k104_30217ed4-82a6-4b6d-b6f6-77fab8faa867.xml, kernel.iofreemdl, wdm/IoFreeMdl
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoFreeMdl
 - wdm/IoFreeMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - IoFreeMdl
---

# IoFreeMdl function


## -description

The <b>IoFreeMdl</b> routine releases a caller-allocated memory descriptor list (MDL).

## -parameters

### -param Mdl 

[in]
Pointer to the MDL to be released.

## -remarks

If a driver allocates an MDL to describe a buffer, it must explicitly release the MDL when operations on the buffer are done.

If the MDL is a partial MDL, <b>IoFreeMdl</b> unmaps any pages that have been mapped to the MDL.

If the physical pages that are described by the MDL are locked, the driver must unlock the pages before it frees the MDL.

This routine frees only the specified MDL. Any MDLs that are chained to this MDL must be explicitly freed through additional calls to this routine. For a code example that shows how to free an MDL chain, see <a href="/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iobuildpartialmdl">IoBuildPartialMdl</a>