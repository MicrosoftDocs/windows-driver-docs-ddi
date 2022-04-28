---
UID: NF:acxstreams.AcxStreamResumeIoWithTag
tech.root: audio
title: AcxStreamResumeIoWithTag
ms.date: 07/14/2021
targetos: Windows
description: The AcxStreamResumeIoWithTag function is used to resume IO for a stream. 
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
 - AcxStreamResumeIoWithTag
f1_keywords:
 - AcxStreamResumeIoWithTag
 - acxstreams/AcxStreamResumeIoWithTag
dev_langs:
 - c++
---

## -description

The **AcxStreamResumeIoWithTag** function is used to resume IO for a stream after it has been stopped. It is similar to [AcxStreamResumeIo](nf-acxstreams-acxstreamresumeio.md) function, but provides the ability to use a Tag that provides additional diagnostic information.

## -parameters

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Tag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

## -returns

Void

## -remarks

### Example

Example usage is shown below.

Sample pending

```cpp

```



## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic