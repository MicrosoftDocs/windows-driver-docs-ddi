---
UID: NF:wdm.KeAddTriageDumpDataBlock
title: KeAddTriageDumpDataBlock function (wdm.h)
description: Adds a triage dump data block to a triage dump data block array.
ms.assetid: 18c54115-6df7-48c9-bcd5-1dfde7591fe5
ms.date: 10/19/2018
keywords: ["KeAddTriageDumpDataBlock function"]
f1_keywords:
 - "wdm/KeAddTriageDumpDataBlock"
 - "KeAddTriageDumpDataBlock"
ms.keywords: KeAddTriageDumpDataBlock
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
topic_type: 
- apiref
api_type: 
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- KeAddTriageDumpDataBlock
targetos: Windows

ms.custom: 19H1
---

# KeAddTriageDumpDataBlock function


## -description

Adds a triage dump data block to a triage dump data block array.

## -parameters

### -param KtriageDumpDataArray
[_Inout_] A pointer to a [**KTRIAGE_DUMP_DATA_ARRAY**](ns-wdm-_ktriage_dump_data_array.md) structure that is the data block array. It is assumed that the caller has already obtained exclusive write to _KtriageDumpDataArray_.

### -param Address
 [_In_] A ULONG_PTR that is the starting address of the data block.

### -param Size
[_In_] The size of the data block, in bytes.

## -returns
Returns STATUS_SUCCESS if the data block was successfully added. Otherwise returns an appropriate [NTSTATUS value](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values). 

## -remarks

## -see-also

[*KeInitializeTriageDumpDataArray***](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keinitializetriagedumpdataarray)

[*KBUGCHECK_REASON_CALLBACK_ROUTINE*](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kbugcheck_reason_callback_routine)
