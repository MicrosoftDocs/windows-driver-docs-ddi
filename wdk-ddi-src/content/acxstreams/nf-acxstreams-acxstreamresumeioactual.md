---
UID: NF:acxstreams.AcxStreamResumeIoActual
tech.root: audio
title: AcxStreamResumeIoActual
ms.date: 02/04/2022
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

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ObjectTag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

### -param Line

The Line number in the driver code that can be displayed for diagnostic purposes.

### -param File

The file name in the driver code that can be displayed for diagnostic purposes.

## -returns

Void

## -remarks

It is not recommended to use this version of the resume IO call, but rather [AcxStreamResumeIoWithTag](nf-acxstreams-acxstreamresumeiowithtag.md).

## -see-also

[acxstreams.h header](index.md)

