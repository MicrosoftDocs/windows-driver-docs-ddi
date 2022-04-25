---
UID: NF:acxstreams.AcxStreamStopIo
tech.root: audio
title: AcxStreamStopIo
ms.date: 02/04/2022
targetos: Windows
description: The AcxStreamStopIo function is used to stop the IO for a stream TBD. 
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
 - AcxStreamStopIo
f1_keywords:
 - AcxStreamStopIo
 - acxstreams/AcxStreamStopIo
dev_langs:
 - c++
---

## -description

The **AcxStreamStopIo** function is used to stop the IO for a stream TBD. 

## -parameters

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

TBD - The following flags are defined to TBD TBD.

TBD - Set to null as no flags are defined.

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxStreamStopIoWithTag](nf-acxstreams-acxstreamstopiowithtag.md).

## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic