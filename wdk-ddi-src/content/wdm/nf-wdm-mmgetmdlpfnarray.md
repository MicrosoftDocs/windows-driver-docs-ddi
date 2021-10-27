---
UID: NF:wdm.MmGetMdlPfnArray
tech.root: 
title: MmGetMdlPfnArray
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: MmGetMdlPfnArray"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - MmGetMdlPfnArray
f1_keywords:
 - MmGetMdlPfnArray
 - wdm/MmGetMdlPfnArray
dev_langs:
 - c++
---

## -description

The **MmGetMdlPfnArray** macro returns a pointer to the beginning of the array of physical page numbers that are associated with a memory descriptor list (MDL).

## -parameters

### -param Mdl [in]


A pointer to an MDL.

## -remarks

Returns a pointer to the beginning of the array of physical page numbers associated with the MDL.
The number of entries in the array is **ADDRESS_AND_SIZE_TO_SPAN_PAGES**(**MmGetMdlVirtualAddress**(_Mdl_), **MmGetMdlByteCount**(_Mdl_)). Each array element is an integer value of type PFN_NUMBER, which is Defined in: Wdm.h as follows:

`cpp typedef ULONG PFN_NUMBER, *PPFN_NUMBER;`

**Note** Changing the contents of the array can cause subtle system problems that are difficult to diagnose. We recommend that you do not read or change the contents of this array.

For pageable memory, the contents of the array are valid only for a buffer locked with [**MmProbeAndLockPages**](./nf-wdm-mmprobeandlockpages.md). For nonpaged pool, the contents of the array are valid only for an MDL updated with [**MmBuildMdlForNonPagedPool**](./nf-wdm-mmbuildmdlfornonpagedpool.md), [**MmAllocatePagesForMdlEx**](./nf-wdm-mmallocatepagesformdlex.md), or [**MmAllocatePagesForMdl**](./nf-wdm-mmallocatepagesformdl.md).

For more information about MDLs, see [Using MDLs](/windows-hardware/drivers/kernel/using-mdls).
