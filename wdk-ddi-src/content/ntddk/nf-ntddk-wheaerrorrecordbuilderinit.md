---
UID: NF:ntddk.WheaErrorRecordBuilderInit
tech.root: kernel
title: WheaErrorRecordBuilderInit (ntddk.h)
ms.date: 03/25/2022
targetos: Windows
description: The WheaErrorRecordBuilderInit function initializes an error record for the record builder helper functions.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.idl: 
req.include-header: Ntddk.h
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
 - ntddk.h
api_name:
 - WheaErrorRecordBuilderInit
f1_keywords:
 - WheaErrorRecordBuilderInit
 - ntddk/WheaErrorRecordBuilderInit
dev_langs:
 - c++
helpviewer_keywords:
 - WheaErrorRecordBuilderInit
---

## -description

The **WheaErrorRecordBuilderInit** function initializes an error record for the record builder helper functions.

## -parameters

### -param Record

Supplies a buffer that holds the error record contents.

### -param RecordLength

Supplies the total buffer size for *Record*.

### -param Severity

Supplies the overall record severity.

### -param Notify

Supplies the **GUID** for the notification type.

## -remarks

## -see-also
