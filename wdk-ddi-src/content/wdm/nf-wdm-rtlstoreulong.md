---
UID: NF:wdm.RtlStoreUlong
tech.root: 
title: RtlStoreUlong
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: RtlStoreUlong"
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
 - RtlStoreUlong
f1_keywords:
 - RtlStoreUlong
 - wdm/RtlStoreUlong
dev_langs:
 - c++
---

## -description

The **RtlStoreUlong** macro stores a ULONG value at a particular address, avoiding alignment faults.

## -parameters

### -param ADDRESS [out]


A pointer to a location in which to store the specified ULONG value.

### -param VALUE [in]


Specifies a ULONG value to be stored.

## -remarks

The caller can be running at any IRQL if _Address_ points to nonpaged pool. Otherwise, the caller must be running at IRQL <= APC_LEVEL.
