---
UID: NF:acxcircuit.AcxCircuitResumeIoWithTag
tech.root: audio
title: AcxCircuitResumeIoWithTag
ms.date: 02/04/2022
targetos: Windows
description: The AcxCircuitResumeIoWithTag function is used to resume circuit IO after it has been stopped. 
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

The **AcxCircuitResumeIoWithTag** function is used to resume circuit IO after it has been stopped. It is different from [AcxCircuitResumeIo](nf-acxcircuit-acxcircuitresumeio.md) in that it can contain additional Tag parameter that is used to display diagnostic information. 

## -parameters

### -param Circuit

An existing ACXCIRCUIT circuit object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Tag

An optional ObjectTag that is a driver-defined value that the framework stores as an identification tag for the ACX driver.

## -remarks


### Example

Example usage is shown below.

TBD - No sample code found.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

