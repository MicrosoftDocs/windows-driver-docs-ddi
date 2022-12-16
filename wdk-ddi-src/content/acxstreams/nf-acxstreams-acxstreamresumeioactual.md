---
UID: NF:acxstreams.AcxStreamResumeIoActual
tech.root: audio
title: AcxStreamResumeIoActual
ms.date: 11/09/2022
targetos: Windows
description: The AcxStreamResumeIoActual function is used to resume IO for a stream.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
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
 - AcxStreamResumeIoActual
f1_keywords:
 - AcxStreamResumeIoActual
 - acxstreams/AcxStreamResumeIoActual
dev_langs:
 - c++
---

## -description

The **AcxStreamResumeIoActual** function is used to resume IO for a stream.

## -parameters

### -param Stream [in]

A pointer to an existing ACXSTREAM Object. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ObjectTag [in, optional]

An optional tag that is a driver-defined value that the framework includes with diagnostic tracing.

### -param Line [in]

The line number in the driver code that can be displayed for diagnostic purposes.

### -param File [in]

The file name in the driver code that can be displayed for diagnostic purposes.

## -remarks

Don't use this version of the resume IO call, but rather [AcxStreamResumeIoWithTag](nf-acxstreams-acxstreamresumeiowithtag.md).

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
