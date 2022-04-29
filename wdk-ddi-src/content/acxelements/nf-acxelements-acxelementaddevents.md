---
UID: NF:acxelements.AcxElementAddEvents
tech.root: audio 
title: AcxElementAddEvents
ms.date: 04/29/2022
targetos: Windows
description: The AcxElementAddEvents function provides the ability to add ACXEVENT event objects to an ACXELEMENT object. 
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

The **AcxElementAddEvents** function provides the ability to add ACXEVENT event objects to an existing ACXELEMENT object.

## -parameters

### -param Element

An existing ACXELEMENT object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param Events

One or more ACXEVENT objects.

### -param EventsCount

The number of events in the Events array.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

Sample Pending

```cpp

```

## -see-also

- [acxelements.h header](index.md)

READY2GO
