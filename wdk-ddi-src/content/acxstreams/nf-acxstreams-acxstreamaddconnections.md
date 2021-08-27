---
UID: NF:acxstreams.AcxStreamAddConnections
tech.root: audio
title: AcxStreamAddConnections
ms.date: 07/09/2021
targetos: Windows
description: AcxStreamAddConnections adds stream connections to existing (new? TBD) streams. These connections are TBD and TBD.
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
 - AcxStreamAddConnections
f1_keywords:
 - AcxStreamAddConnections
 - acxstreams/AcxStreamAddConnections
dev_langs:
 - c++
---

## -description

AcxStreamAddConnections adds stream connections to existing (new? TBD) streams. These connections are TBD and TBD.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM Object that represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Connections

An [ACX_CONNECTION structure]() that contains the TBD.

TODO: DocsTeam - need link to this topic when ACXPIN header is documented.

### -param ConnectionsCount

The the TBD- (0 or 1?) based number of connections  that are TBD in the stream.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No sample code or unit tests were located

```cpp

```

## -see-also

[acxstreams.h header](index.md)

