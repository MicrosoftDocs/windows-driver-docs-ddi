---
UID: NF:acxcircuit.AcxCircuitStopIo
tech.root: audio
title: AcxCircuitStopIo
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitStopIo function is used to signal to the operating system to temporarily stop circuit I/O.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **AcxCircuitStopIo** function is used to signal to the operating system to temporarily stop circuit I/O. This allows the driver a short period of time to run time sensitive task, and resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Stop IO flags defined by the [ACX_STOP_IO_FLAGS enumeration](ne-acxcircuit-acx_stop_io_flags.md).
Currently no flags are defined, so set this to `AcxStopIoNoFlags`.

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxCircuitStopIoWithTag macro](nf-acxcircuit-acxcircuitstopiowithtag.md) as it provides additional diagnostic information by using a Tag.

### Example

Example usage is shown below.

```cpp
    // Temporarily disable this circuit's I/Os while we are updating the 
    // formats. This thread cannot be an I/O dispatched thread else we deadlock.
    //
    status = AcxCircuitStopIo(circuit, AcxStopIoNoFlags);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxCircuitStopIoWithTag macro](nf-acxcircuit-acxcircuitstopiowithtag.md)
- [acxcircuit.h header](index.md)
