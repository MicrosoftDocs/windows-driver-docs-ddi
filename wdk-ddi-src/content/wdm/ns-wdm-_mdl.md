---
UID: NS:wdm._MDL
title: _MDL (wdm.h)
description: An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL).
old-location: kernel\mdl.htm
tech.root: kernel
ms.assetid: 71524333-dd5d-4f0b-8dd3-034ea926bc93
ms.date: 04/30/2018
ms.keywords: "*PMDLX, MDL, MDL structure [Kernel-Mode Driver Architecture], PMDL, _MDL, kernel.mdl, kstruct_c_2c589a9a-d775-4fa6-8a37-37212798a215.xml, wdm/MDL"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- MDL
product:
- Windows
targetos: Windows
req.typenames: MDL, PMDL
---

# _MDL structure


## -description


An <b>MDL</b> structure is a partially opaque structure that represents a memory descriptor list (MDL).


## -struct-fields




### -field Next

Pointer to the next MDL in an MDL chain. For more information about MDL chains, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.


### -field Size

 


### -field MdlFlags

 


### -field Process

 


### -field MappedSystemVa

 


### -field StartVa

 


### -field ByteCount

 


### -field ByteOffset

 




## -remarks



An MDL describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmgetmdlbytecount">MmGetMdlByteCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlByteOffset</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlPfnArray</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmGetMdlVirtualAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">MmInitializeMdl</a>
 

 

