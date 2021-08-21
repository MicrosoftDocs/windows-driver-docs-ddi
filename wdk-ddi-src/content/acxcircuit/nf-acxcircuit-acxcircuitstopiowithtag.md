---
UID: NF:acxcircuit.AcxCircuitStopIoWithTag
tech.root: audio
title: AcxCircuitStopIoWithTag
ms.date: 08/20/2021
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitStopIoWithTag
f1_keywords:
 - AcxCircuitStopIoWithTag
 - acxcircuit/AcxCircuitStopIoWithTag
dev_langs:
 - c++
---

## -description

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).


### -param Flags

TBD
TBD - Are any flags defined?
TBD

### -param Tag

An optional Tag that is used to TBD. (can be displayed for diagnostic information??? TBD)

## -remarks

TBD - Add resume to this table?

ACX Events are analogous to KS states as described in this table.

| Start State | End State | ACX Driver Event Called | Notes                                                 |
|-------------|-----------|-------------------------|-------------------------------------------------------|
| STOP        | ACQUIRE   | PrepareHardware         | Driver performs hardware allocations and preparations |
| ACQUIRE     | PAUSE     | Pause                   |                                                       |
| PAUSE       | RUN       | Run                     |                                                       |
| RUN         | PAUSE     | Pause                   |                                                       |
| PAUSE       | ACQUIRE   | No call                 |                                                       |
| ACQUIRE     | STOP      | ReleaseHardware         | Driver releases hardware allocations                  |

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

