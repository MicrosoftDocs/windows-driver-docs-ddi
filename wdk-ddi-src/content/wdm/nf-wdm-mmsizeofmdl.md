---
UID: NF:wdm.MmSizeOfMdl
title: MmSizeOfMdl function (wdm.h)
description: The MmSizeOfMdl routine returns the number of bytes to allocate for an MDL describing a given address range.
old-location: kernel\mmsizeofmdl.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmSizeOfMdl function"]
ms.keywords: MmSizeOfMdl, MmSizeOfMdl routine [Kernel-Mode Driver Architecture], k106_7cddc848-8b01-4a6a-b5b1-977f2386fc21.xml, kernel.mmsizeofmdl, wdm/MmSizeOfMdl
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - MmSizeOfMdl
 - wdm/MmSizeOfMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmSizeOfMdl
---

# MmSizeOfMdl function


## -description

The <b>MmSizeOfMdl</b> routine returns the number of bytes to allocate for an MDL describing a given address range.

## -parameters

### -param Base 

[in]
Pointer to the base virtual address for the range.

### -param Length 

[in]
Supplies the size, in bytes, of the range.

## -returns

<b>MmSizeOfMdl</b> returns the number of bytes required to contain the MDL.

## -remarks

Memory for the MDL itself must be allocated from nonpaged pool.

## -see-also

<a href="/windows-hardware/drivers/kernel/mmcreatemdl">MmCreateMdl</a>



[MmInitializeMdl](./nf-wdm-mminitializemdl.md)