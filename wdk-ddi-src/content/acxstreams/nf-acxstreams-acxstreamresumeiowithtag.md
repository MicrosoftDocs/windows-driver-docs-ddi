---
UID: NF:acxstreams.AcxStreamResumeIoWithTag
tech.root: audio
title: AcxStreamResumeIoWithTag
ms.date: 07/14/2021
targetos: Windows
description: The AcxStreamResumeIoWithTag function is used to resume IO for a stream TBD. 
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

The AcxStreamResumeIoWithTag function is used to resume IO for a stream TBD. It is similar to [AcxStreamResumeIo](nf-acxstreams-acxstreamresumeio.md) function, but provides the ability to use a Tag that TBD.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Tag

An optional Tag that is used to TBD. (can be displayed for diagnostic information??? TBD)


## -returns

Void


## -remarks

### Example

Example usage is shown below.

TBD No example code found

TBD No internal implementation API code found


```cpp

```



## -see-also

[acxstreams.h header](index.md)

