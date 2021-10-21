---
UID: NF:wdm.RtlRetrieveUlong
tech.root: 
title: RtlRetrieveUlong
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: RtlRetrieveUlong"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: See Remarks
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
 - RtlRetrieveUlong
f1_keywords:
 - RtlRetrieveUlong
 - wdm/RtlRetrieveUlong
dev_langs:
 - c++
---

## -description

The **RtlRetrieveUlong** macro retrieves a ULONG value from the source address, avoiding alignment faults. The destination address is assumed to be aligned.

## -parameters

### -param DEST_ADDRESS [out]


Pointer to a ULONG-aligned location in which to store the ULONG value.

### -param SRC_ADDRESS [in]


Pointer to a location from which to retrieve the ULONG value.

## -remarks

Callers of **RtlRetrieveUlong** can be running at any IRQL if the given addresses are in nonpaged pool. Otherwise, the caller must be running at IRQL <= APC_LEVEL.
