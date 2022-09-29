---
UID: NS:wdm._MDL
title: _MDL (wdm.h)
description: An MDL structure is a partially opaque structure that represents a memory descriptor list (MDL).
old-location: kernel\mdl.htm
tech.root: kernel
ms.date: 08/15/2022
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

An **MDL** structure is a partially opaque structure that represents a memory descriptor list (MDL).

## -struct-fields

### -field Next

Pointer to the next MDL in an MDL chain. For more information about MDL chains, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

### -field Size

### -field MdlFlags

### -field Process

### -field MappedSystemVa

### -field StartVa

### -field ByteCount

### -field ByteOffset

## -remarks

An MDL describes the layout of a virtual memory buffer in physical memory. For more information, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).

## -see-also

- [IoAllocateMdl](./nf-wdm-ioallocatemdl.md)
- [MmGetMdlByteCount](./nf-wdm-mmgetmdlbytecount.md)
- [MmGetMdlByteOffset](./nf-wdm-mmgetmdlbyteoffset.md)
- [MmGetMdlPfnArray](./nf-wdm-mmgetmdlpfnarray.md)
- [MmGetMdlVirtualAddress](./nf-wdm-mmgetmdlvirtualaddress.md)
- [MmInitializeMdl](./nf-wdm-mminitializemdl.md)
