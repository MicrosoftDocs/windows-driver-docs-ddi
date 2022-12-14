---
UID: NF:acxcircuit.AcxCircuitStopIoWithTag
tech.root: audio
title: AcxCircuitStopIoWithTag
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitStopIoWithTag function is used to signal to the operating system to temporarily stop circuit I/O. 
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
 - AcxCircuitStopIoWithTag
f1_keywords:
 - AcxCircuitStopIoWithTag
 - acxcircuit/AcxCircuitStopIoWithTag
dev_langs:
 - c++
---

## -description

The **AcxCircuitStopIoWithTag** function is used to signal to the operating system to temporarily stop circuit I/O. This allows the driver a short period of time to run time sensitive tasks, and then resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Circuit

An existing *ACXCIRCUIT* circuit object.  (For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Stop IO flags defined by the [ACX_STOP_IO_FLAGS enumeration](ne-acxcircuit-acx_stop_io_flags.md).

Currently no flags are defined, set this to `AcxStopIoNoFlags`.

### -param Tag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver. Specify the pointer of the object taking the reference.

## -remarks

### Example

Example usage is shown below.

Sample pending.

```cpp

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
