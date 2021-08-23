---
UID: NF:acxcircuit.AcxCircuitResumeIoWithTag
tech.root: audio
title: AcxCircuitResumeIoWithTag
ms.date: 08/23/2021
targetos: Windows
description: TBD - The AcxCircuitResumeIoWithTag function is used to resume circuit IO after it has been stopped. 
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
 - AcxCircuitResumeIoWithTag
f1_keywords:
 - AcxCircuitResumeIoWithTag
 - acxcircuit/AcxCircuitResumeIoWithTag
dev_langs:
 - c++
---

## -description

TBD - The AcxCircuitResumeIoWithTag function is used to resume circuit IO after it has been stopped. It is different from [AcxCircuitResumeIo](nf-acxcircuit-acxcircuitresumeio.md) in that it can contain additional Tag parameter that is used to TBD TBD TBD display diagnostic information TBD locate a WaveFormat stream tag ???. 

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).


### -param Tag

An optional Tag that is used to TBD. (can be displayed for diagnostic information??? TBD)

## -remarks

TBD - Add resume and stop to this table?

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

TBD - No sample code or unit test code found.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

