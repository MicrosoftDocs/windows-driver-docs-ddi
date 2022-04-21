---
UID: NF:acxcircuit.AcxCircuitResumeIoActual
tech.root: audio
title: AcxCircuitResumeIoActual
ms.date: 02/04/2022
targetos: Windows
description: The AcxCircuitResumeIoActual function is used to resume circuit IO after it has been stopped.
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
 - AcxCircuitResumeIoActual
f1_keywords:
 - AcxCircuitResumeIoActual
 - acxcircuit/AcxCircuitResumeIoActual
dev_langs:
 - c++
---

## -description

The **AcxCircuitResumeIoActual** function is used to resume circuit IO after it has been stopped. 

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ObjectTag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

### -param Line

The Line number in the driver code that can be displayed for diagnostic purposes.

### -param File

The file name in the driver code that can be displayed for diagnostic purposes.

## -remarks

It is not recommended to use this version of the stop IO call, but rather [AcxCircuitResumeIoWithTag macro](nf-acxcircuit-acxcircuitresumeiowithtag.md) as it provides additional diagnostic information by using a Tag.

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic