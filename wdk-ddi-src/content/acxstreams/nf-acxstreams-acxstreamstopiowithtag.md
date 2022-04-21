---
UID: NF:acxstreams.AcxStreamStopIoWithTag
tech.root: audio
title: AcxStreamStopIoWithTag
ms.date: 02/04/2022
targetos: Windows
description: The AcxStreamStopIoWithTag function is used to signal to the operating system to temporarily stop stream IO. 
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
 - AcxStreamStopIoWithTag
f1_keywords:
 - AcxStreamStopIoWithTag
 - acxstreams/AcxStreamStopIoWithTag
dev_langs:
 - c++
---

## -description

The **AcxStreamStopIoWithTag** function is used used to signal to the operating system to temporarily stop stream IO. This allows the driver a short period of time to run time sensitive tasks, and then resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM Object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

TBD - The following flags are defined to TBD TBD.

TBD - Set to null as no flags are defined.

### -param Tag

An optional Tag that is used to TBD. (can be displayed for diagnostic information??? TBD)

## -remarks

### Example

Example usage is shown below.

TBD No example code found

```cpp

```


## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic