---
UID: NF:wdm.KeInitializeTriageDumpDataArray
title: KeInitializeTriageDumpDataArray function
description: Initializes a triage dump data block array.
tech.root: devtest
ms.date: 10/19/2018
keywords: ["KeInitializeTriageDumpDataArray function"]
ms.keywords: KeInitializeTriageDumpDataArray
req.header: wdm.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - KeInitializeTriageDumpDataArray
 - wdm/KeInitializeTriageDumpDataArray
topic_type:
 - apiref
api_type:
 - apiref
api_location:
 - wdm.h
api_name:
 - KeInitializeTriageDumpDataArray
---

# KeInitializeTriageDumpDataArray function


## -description

The **KeInitializeTriageDumpDataArray** function initializes a triage dump data block array.

## -parameters

### -param KtriageDumpDataArray

 A pointer to a [**KTRIAGE_DUMP_DATA_ARRAY**](ns-wdm-_ktriage_dump_data_array.md) structure that is the data block array. It is assumed that the caller has already obtained exclusive write to _KtriageDumpDataArray_.  The array must be allocated from non-paged memory.

### -param Size

Specifies the size, in bytes, of the uninitialized triage dump data array.

## -returns

This function returns NTSTATUS.

## -remarks

## -see-also

[*KeAddTriageDumpDataBlock*](./nf-wdm-keaddtriagedumpdatablock.md)

[*KBUGCHECK_REASON_CALLBACK_ROUTINE*](./nc-wdm-kbugcheck_reason_callback_routine.md)
