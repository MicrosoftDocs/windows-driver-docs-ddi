---
UID: NF:fltkernel.FltFreePoolAlignedWithTag
title: FltFreePoolAlignedWithTag function (fltkernel.h)
description: The FltFreePoolAlignedWithTag routine frees a cache-aligned buffer that was allocated by a previous call to FltAllocatePoolAlignedWithTag.
old-location: ifsk\fltfreepoolalignedwithtag.htm
tech.root: ifsk
ms.assetid: 295a34e4-734e-41ba-bf2e-378333c14e2c
ms.date: 04/16/2018
keywords: ["FltFreePoolAlignedWithTag function"]
ms.keywords: FltApiRef_e_to_o_dc83e564-1331-48f0-ad7e-8cdeaa677952.xml, FltFreePoolAlignedWithTag, FltFreePoolAlignedWithTag routine [Installable File System Drivers], fltkernel/FltFreePoolAlignedWithTag, ifsk.fltfreepoolalignedwithtag
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: See Remarks section.
targetos: Windows
req.typenames: 
f1_keywords:
 - FltFreePoolAlignedWithTag
 - fltkernel/FltFreePoolAlignedWithTag
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltFreePoolAlignedWithTag
---

# FltFreePoolAlignedWithTag function


## -description

The <b>FltFreePoolAlignedWithTag</b> routine frees a cache-aligned buffer that was allocated by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>.

## -parameters

### -param Instance 

[in]
Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. Must be the same instance pointer as the one used in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>.

### -param Buffer 

[in]
Address of the block of pool memory to be freed.

### -param Tag 

[in]
Tag used to mark the pool block. Must be the same tag as the one used in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>.

## -returns

None

## -remarks

The memory that the <i>Buffer</i> parameter points to must not be accessed after it is freed by <b>FltFreePoolAlignedWithTag</b>. 

The caller of <b>FltFreePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL if a <b>NonPaged</b><i>XxxPoolType</i> value was specified when the memory was allocated. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatepoolalignedwithtag">FltAllocatePoolAlignedWithTag</a>

