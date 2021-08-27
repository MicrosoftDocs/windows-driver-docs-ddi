---
UID: NF:acxcircuit.AcxCircuitStopIo
tech.root: audio
title: AcxCircuitStopIo
ms.date: 08/23/2021
targetos: Windows
description: TBD - The AcxCircuitStopIo function is used to stop circuit IO after it has been in a run or TBD pause??? state.
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
 - AcxCircuitStopIo
f1_keywords:
 - AcxCircuitStopIo
 - acxcircuit/AcxCircuitStopIo
dev_langs:
 - c++
---

## -description

TBD - The AcxCircuitStopIo function is used to stop circuit IO after it has been in a run or TBD pause??? state.

## -parameters

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Stop IO flags defined by the [ACX_STOP_IO_FLAGS enumeration](ne-acxcircuit-acx_stop_io_flags.md).
Currently no flags are defined, so set this to `AcxStopIoNoFlags`. 

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

```cpp
    // Temporarily disable this circuit's I/Os while we are updating the 
    // formats. This thread cannot be an I/O dispatched thread else we deadlock.
    //
    status = AcxCircuitStopIo(circuit, AcxStopIoNoFlags);
```

## -see-also

[acxcircuit.h header](index.md)

