---
UID: NS:wdm._MDL
title: _MDL (wdm.h)
description: An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL).
old-location: kernel\mdl.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MDL structure"]
ms.keywords: "*PMDLX, MDL, MDL structure [Kernel-Mode Driver Architecture], PMDL, _MDL, kernel.mdl, kstruct_c_2c589a9a-d775-4fa6-8a37-37212798a215.xml, wdm/MDL"
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
targetos: Windows
req.typenames: MDL, PMDL
f1_keywords:
 - _MDL
 - wdm/_MDL
 - PMDL
 - wdm/PMDL
 - MDL
 - wdm/MDL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _MDL
 - PMDL
 - MDL
---

# _MDL structure


## -description

An <b>MDL</b> structure is a partially opaque structure that represents a memory descriptor list (MDL).

## -struct-fields

### -field Next

Pointer to the next MDL in an MDL chain. For more information about MDL chains, see <a href="/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

### -field Size

### -field MdlFlags

### -field Process

### -field MappedSystemVa

### -field StartVa

### -field ByteCount

### -field ByteOffset

## -remarks

An MDL describes the layout of a virtual memory buffer in physical memory. For more information, see <a href="/windows-hardware/drivers/kernel/using-mdls">Using MDLs</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmgetmdlbytecount">MmGetMdlByteCount</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlbyteoffset">MmGetMdlByteOffset</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlpfnarray">MmGetMdlPfnArray</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mmgetmdlvirtualaddress">MmGetMdlVirtualAddress</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer#mminitializemdl">MmInitializeMdl</a>

