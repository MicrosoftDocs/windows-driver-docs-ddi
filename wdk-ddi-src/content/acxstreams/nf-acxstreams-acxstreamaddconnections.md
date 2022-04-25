---
UID: NF:acxstreams.AcxStreamAddConnections
tech.root: audio
title: AcxStreamAddConnections
ms.date: 02/02/2022
targetos: Windows
description: The AcxStreamAddConnections function adds connections to an existing ACX stream. 
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

The AcxStreamAddConnections function adds connections to an existing ACX stream. 

## -parameters

### -param Stream

A pointer to a location that that contains an existing ACXSTREAM Object. An ACXSTREAM Object that represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Connections

An [ACX_CONNECTION structure](..\acxpin\ns-acxpin-acx_connection.md) that contains information about the connections to add the stream.

### -param ConnectionsCount

The number of connections that are in the stream. This is a 1 based count. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No sample code or unit tests were located

```cpp

```

## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic