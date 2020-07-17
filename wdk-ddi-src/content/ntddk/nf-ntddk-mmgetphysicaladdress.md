---
UID: NF:ntddk.MmGetPhysicalAddress
title: MmGetPhysicalAddress function (ntddk.h)
description: The MmGetPhysicalAddress routine returns the physical address corresponding to a valid nonpaged virtual address.
old-location: kernel\mmgetphysicaladdress.htm
tech.root: kernel
ms.assetid: 2381c1c2-d7fc-4cb2-bbdf-2a95c78c34d0
ms.date: 04/30/2018
keywords: ["MmGetPhysicalAddress function"]
ms.keywords: MmGetPhysicalAddress, MmGetPhysicalAddress routine [Kernel-Mode Driver Architecture], k106_1dc50500-ccd1-41a9-8a6c-55e3e283b00b.xml, kernel.mmgetphysicaladdress, ntddk/MmGetPhysicalAddress
f1_keywords:
 - "ntddk/MmGetPhysicalAddress"
 - "MmGetPhysicalAddress"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmGetPhysicalAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmGetPhysicalAddress function


## -description


The <b>MmGetPhysicalAddress</b> routine returns the physical address corresponding to a valid nonpaged virtual address.


## -parameters




### -param BaseAddress [in]

Pointer to the virtual address for which to return the physical address. 


## -returns



<b>MmGetPhysicalAddress</b> returns the physical address that corresponds to the given virtual address.

Do not use this routine to obtain physical addresses for use with DMA operations. For information about the proper techniques for performing DMA operations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/adapter-objects-and-dma">Adapter Objects and DMA</a>.




## -remarks



Callers of <b>MmGetPhysicalAddress</b> can be running at any IRQL, provided that the <i>BaseAddress</i> value is valid.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmisaddressvalid">MmIsAddressValid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mmcreatemdl">MmIsNonPagedSystemAddressValid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmapiospace">MmMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>
 

 

