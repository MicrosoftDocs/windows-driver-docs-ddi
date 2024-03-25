---
UID: NF:acxstreams.AcxStreamStopIo
tech.root: audio
title: AcxStreamStopIo
ms.date: 12/16/2022
targetos: Windows
description: The AcxStreamStopIo function is used to temporarily stop the IO for a stream.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - acxstreams.h
api_name:
 - AcxStreamStopIo
f1_keywords:
 - AcxStreamStopIo
 - acxstreams/AcxStreamStopIo
dev_langs:
 - c++
---

## -description

The **AcxStreamStopIo** function is used to stop the IO for a stream.

## -parameters

### -param Stream

An existing ACXSTREAM Object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Set to AcxStopIoNoFlags.

## -remarks

Do not call AcxStreamStopIo from an I/O dispatched thread. This will cause a deadlock.

It is not recommended to use this version of the stop IO call, but rather [AcxStreamStopIoWithTag](nf-acxstreams-acxstreamstopiowithtag.md).

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
