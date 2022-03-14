---
UID: NF:wdm.ExFreeToLookasideListEx~r1
tech.root: kernel
title: ExFreeToLookasideListEx (wdm.h)
ms.date: 03/14/2022
targetos: Windows
description: This topic describes the ExFreeToLookasideListEx function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN11_NEXT
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
 - ExFreeToLookasideListEx
f1_keywords:
 - ExFreeToLookasideListEx
 - wdm/ExFreeToLookasideListEx
dev_langs:
 - c++
helpviewer_keywords:
 - ExFreeToLookasideListEx
---

## -description

This topic describes the **ExFreeToLookasideListEx** function.

## -parameters

### -param Lookaside [in,out]

Defines the **PLOOKASIDE_LIST_EX** parameter *Lookaside*. Supplies a pointer to a **LOOKASIDE_LIST_EX** structure.

### -param Entry

Defines the **PVOID** parameter *Entry*. Supplies a pointer to the entry that is inserted in the lookaside list.

## -remarks

This function inserts (pushes) the specified entry into the specified lookaside list.

## -see-also
