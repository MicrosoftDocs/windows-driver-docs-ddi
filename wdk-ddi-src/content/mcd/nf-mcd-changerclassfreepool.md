---
UID: NF:mcd.ChangerClassFreePool
title: ChangerClassFreePool function (mcd.h)
description: The ChangerClassFreePool routine frees pool memory previously allocated using ChangerClassAllocatePool.
old-location: storage\changerclassfreepool.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ChangerClassFreePool function"]
ms.keywords: ChangerClassFreePool, ChangerClassFreePool routine [Storage Devices], chgrclas_3f5fb8a4-3c85-4dde-80c9-f8e001b7b3bd.xml, mcd/ChangerClassFreePool, storage.changerclassfreepool
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
req.target-type: Desktop
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - ChangerClassFreePool
 - mcd/ChangerClassFreePool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Mcd.lib
 - Mcd.dll
api_name:
 - ChangerClassFreePool
---

# ChangerClassFreePool function


## -description

The <b>ChangerClassFreePool</b> routine frees pool memory previously allocated using <a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerclassallocatepool">ChangerClassAllocatePool</a>.

## -parameters

### -param PoolToFree 

[in]
Pointer to the block of memory to be freed.

## -see-also

<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerclassallocatepool">ChangerClassAllocatePool</a>
