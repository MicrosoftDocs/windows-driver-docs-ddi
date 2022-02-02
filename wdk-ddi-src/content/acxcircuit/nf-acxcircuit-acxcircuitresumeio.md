---
UID: NF:acxcircuit.AcxCircuitResumeIo
tech.root: audio
title: AcxCircuitResumeIo
ms.date: 08/20/2021
targetos: Windows
description: The AcxCircuitResumeIo function is used to resume circuit IO after it has been stopped.
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
 - AcxCircuitResumeIo
f1_keywords:
 - AcxCircuitResumeIo
 - acxcircuit/AcxCircuitResumeIo
dev_langs:
 - c++
---

## -description

The AcxCircuitResumeIo function is used to resume circuit IO after it has been stopped.

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

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

    BOOLEAN                         stoppedIo = FALSE;
    circuit = AcxPinGetCircuit(pin);

    //
    // Temporarily disable this circuit's I/Os while we are updating the 
    // formats. This thread cannot be an I/O dispatched thread else we deadlock.
    //
    status = AcxCircuitStopIo(circuit, AcxStopIoNoFlags);
    if (!NT_SUCCESS(status))
    {
        HDTrace(TRACE_LEVEL_ERROR, FLAG_INFO, 
                "Failed to stop I/O on circuit %p, %!STATUS!", 
                circuit, status);
        ASSERT(FALSE);
        goto exit;
    }
    stoppedIo = TRUE;

   // Code to update format list not shown here 

...

    if (stoppedIo)
    {
        AcxCircuitResumeIo(circuit);
        stoppedIo = FALSE;
    }
```

## -see-also

[acxcircuit.h header](index.md)

