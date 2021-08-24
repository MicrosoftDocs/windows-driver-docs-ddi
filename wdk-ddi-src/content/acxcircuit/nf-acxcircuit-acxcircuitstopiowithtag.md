---
UID: NF:acxcircuit.AcxCircuitStopIoWithTag
tech.root: audio
title: AcxCircuitStopIoWithTag
ms.date: 08/20/2021
targetos: Windows
description: TBD - The AcxCircuitStopIoWithTag function is used to stop circuit IO after it has been in a run or TBD pause??? state.
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

TBD - The AcxCircuitStopIoWithTag function is used to stop circuit IO after it has been in a run or TBD pause??? state. It is different from [AcxCircuitStopIo](nf-acxcircuit-acxcircuitstopio.md) in that it can contain additional Tag parameter that is used to TBD TBD TBD display diagnostic information - locate the stream TBD ???. 

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param Flags

Stop IO flags defined by the [ACX_STOP_IO_FLAGS enumeration](ne-acxcircuit-acx_stop_io_flags.md).
TBD - Currently no flags are defined, so set this to `AcxStopIoNoFlags`. 

### -param Tag

An optional Tag that is used to locate the TBD TBD. (can be displayed for diagnostic information??? TBD)

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

TBD - No sample or unit test code found

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

