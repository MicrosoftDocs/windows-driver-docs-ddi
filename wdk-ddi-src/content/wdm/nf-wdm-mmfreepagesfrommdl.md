---
UID: NF:wdm.MmFreePagesFromMdl
title: MmFreePagesFromMdl function (wdm.h)
description: The MmFreePagesFromMdl routine frees all the physical pages that are described by an MDL that was created by the MmAllocatePagesForMdl routine.
old-location: kernel\mmfreepagesfrommdl.htm
tech.root: kernel
ms.assetid: bde26b75-9eae-494b-b943-f1e9534c5f7a
ms.date: 04/30/2018
keywords: ["MmFreePagesFromMdl function"]
ms.keywords: MmFreePagesFromMdl, MmFreePagesFromMdl routine [Kernel-Mode Driver Architecture], k106_4263f517-edab-4378-b316-ce344676d7e6.xml, kernel.mmfreepagesfrommdl, wdm/MmFreePagesFromMdl
f1_keywords:
 - "wdm/MmFreePagesFromMdl"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmFreePagesFromMdl
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmFreePagesFromMdl function


## -description


The <b>MmFreePagesFromMdl</b> routine frees all the physical pages that are described by an MDL that was created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a> routine. 


## -parameters




### -param MemoryDescriptorList [in]

Pointer to an MDL that was created by <b>MmAllocatePagesForMdl</b>.


## -remarks



<b>MmFreePagesFromMdl</b> can only be used to free the memory pages that are described by an MDL that was created by <b>MmAllocatePagesForMdl</b>.

After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> to release the memory that was allocated for the MDL structure.

<b>MmFreePagesFromMdl</b> runs at IRQL <= APC_LEVEL. For Windows Server 2008 and later versions of the Windows operating system, you can also call this routine at DISPATCH_LEVEL. However, you can improve driver performance by calling at IRQL <= APC_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a>
 

 

