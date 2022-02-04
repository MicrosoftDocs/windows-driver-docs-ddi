---
UID: NF:acxelements.AcxElementAddEvents
tech.root: audio 
title: AcxElementAddEvents
ms.date: 09/23/2021
targetos: Windows
description: TBD - The AcxElementAddEvents function provides the ability to add ACXEVENT event objects to an ACXELEMENT object. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
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
 - acxelements.h
api_name:
 - AcxElementAddEvents
f1_keywords:
 - AcxElementAddEvents
 - acxelements/AcxElementAddEvents
dev_langs:
 - c++
---

## -description

TBD - The AcxElementAddEvents function provides the ability to add ACXEVENT event objects to an ACXELEMENT object. 

## -parameters

### -param Element

TBD - An ACXELEMENT object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Events

TBD - An ACXEVENT object. TBD - array?

### -param EventsCount

A count of the events. This is a 1 based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No example code found

```cpp

```

## -see-also

[acxelements.h header](index.md)

