---
UID: NF:wdm.MmInitializeMdl
tech.root: 
title: MmInitializeMdl
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: MmInitializeMdl"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - MmInitializeMdl
f1_keywords:
 - MmInitializeMdl
 - wdm/MmInitializeMdl
dev_langs:
 - c++
---

## -description

The **MmInitializeMdl** macro initializes the header of an MDL.

## -parameters

### -param MemoryDescriptorList [in]


A pointer to the buffer to initialize as an MDL. For more information, see the following section.

### -param BaseVa [in]


A pointer to the base virtual address of a buffer.

### -param Length [in]


Specifies the length, in bytes, of the buffer to be described by the MDL. This routine supports a maximum buffer length of MAXULONG bytes.

## -remarks

The buffer that _MemoryDescriptorList_ points to must be allocated in nonpaged memory.
The size, in bytes, of this buffer must be at least **sizeof**(MDL) + **sizeof**(PFN_NUMBER) * **ADDRESS_AND_SIZE_TO_SPAN_PAGES**(_BaseVa_, _Length_).
