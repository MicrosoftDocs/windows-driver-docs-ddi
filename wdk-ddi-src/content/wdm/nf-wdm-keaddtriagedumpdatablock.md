---
UID: NF:wdm.KeAddTriageDumpDataBlock
title: KeAddTriageDumpDataBlock function
author: windows-driver-content
description: Adds a triage dump data block to a triage dump data block array.
ms.assetid: 18c54115-6df7-48c9-bcd5-1dfde7591fe5
ms.author: windowsdriverdev
ms.date: 
ms.topic: function
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
topictype: 
-	apiref
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	KeAddTriageDumpDataBlock
product: Windows
targetos: Windows

---

# KeAddTriageDumpDataBlock function


## -description

Adds a triage dump data block to a triage dump data block array.

## -parameters

### -param KtriageDumpDataArray
[_Inout_] A pointer to a [**KTRIAGE_DUMP_DATA_ARRAY**](ns-wdm-_ktriage_dump_data_array.md) structure that is the data block array. It is assumed that the caller has already obtained exclusive write to _KtriageDumpDataArray_.

### -param MaxDataSize
[_In_] The maximum data size of the array pointed to by _KtriageDumpDataArray_.

### -param Address
 [_In_] A ULONG_PTR that is the starting address if the data block.

### -param Size
[_In_] The size of the data block, in bytes.

## -returns
Returns STATUS_SUCCESS if the data block was successfully added. Otherwise returns an appropriate [NTSTATUS value](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values). 

## -remarks

## -see-also