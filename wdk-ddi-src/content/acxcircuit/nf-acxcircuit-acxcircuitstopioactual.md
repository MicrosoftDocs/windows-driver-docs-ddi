---
UID: NF:acxcircuit.AcxCircuitStopIoActual
tech.root: audio
title: AcxCircuitStopIoActual
ms.date: 02/04/2022
targetos: Windows
description: TBD - The AcxCircuitStopIoActual function is used to stop circuit IO after it has been in a run or TBD pause??? state.
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
 - AcxCircuitStopIoActual
f1_keywords:
 - AcxCircuitStopIoActual
 - acxcircuit/AcxCircuitStopIoActual
dev_langs:
 - c++
---

## -description

The **AcxCircuitStopIoActual** function is used to signal to the operating system to temporarily stop circuit IO. This allows the driver a short period of time to run time sensitive tasks, and then resume IO after the execution of time sensitive code is complete.

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Flags

Stop IO flags defined by the [ACX_STOP_IO_FLAGS enumeration](ne-acxcircuit-acx_stop_io_flags.md).
Currently no flags are defined, so set this to `AcxStopIoNoFlags`. 

### -param ObjectTag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

### -param Line

The Line number in the driver code that can be displayed for diagnostic purposes.

### -param File

The file name in the driver code that can be displayed for diagnostic purposes.


## -returns

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxCircuitStopIoWithTag macro](nf-acxcircuit-acxcircuitstopiowithtag.md).


## -see-also

 [AcxCircuitStopIo](nf-acxcircuit-acxcircuitstopio.md) 

[acxcircuit.h header](index.md)

