---
UID: NF:acxcircuit.AcxCircuitResumeIo
tech.root: audio
title: AcxCircuitResumeIo
ms.date: 07/28/2022
targetos: Windows
description: The AcxCircuitResumeIo function is used to resume circuit I/O after it has been temporarily stopped.
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

The **AcxCircuitResumeIo** function is used to resume circuit I/O after it has been temporarily stopped.

## -parameters

### -param Circuit

An existing ACXCIRCUIT object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxCircuitResumeIoWithTag macro](nf-acxcircuit-acxcircuitresumeiowithtag.md) as it provides additional diagnostic information by using a Tag.

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

- [AcxCircuitResumeIoWithTag macro](nf-acxcircuit-acxcircuitresumeiowithtag.md)

- [acxcircuit.h header](index.md)


