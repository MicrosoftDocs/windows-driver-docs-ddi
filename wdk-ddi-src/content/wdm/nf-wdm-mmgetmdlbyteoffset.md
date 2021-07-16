---
UID: NF:wdm.MmGetMdlByteOffset
tech.root: 
title: MmGetMdlByteOffset
ms.date: 07/16/2021
targetos: Windows
description: 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level (see Remarks)
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
 - MmGetMdlByteOffset
f1_keywords:
 - MmGetMdlByteOffset
 - wdm/MmGetMdlByteOffset
dev_langs:
 - c++
---

## -description

The **MmGetMdlByteOffset** macro returns the byte offset within the initial page of the buffer described by the given MDL.

## -parameters

### -param Mdl

[in]
Pointer to an MDL.

## -remarks

**MmGetMdlByteOffset** returns the offset in bytes.

Callers of **MmGetMdlByteOffset** can be running at any IRQL. Usually, callers are running at IRQL <= DISPATCH_LEVEL.


