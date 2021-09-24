---
UID: NF:acxelements.AcxElementGetContainer
tech.root: audio 
title: AcxElementGetContainer
ms.date: 09/23/2021
targetos: Windows
description: TBD - The AcxElementGetContainer function retrieves the associated container for the provided ACX element. 
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
 - AcxElementGetContainer
f1_keywords:
 - AcxElementGetContainer
 - acxelements/AcxElementGetContainer
dev_langs:
 - c++
---

## -description

TBD - The AcxElementGetContainer function retrieves the associated container for the provided ACX element. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Element

TBD - An ACXELEMENT object. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACXCIRCUIT          circuit     = (ACXCIRCUIT)AcxElementGetContainer((ACXELEMENT)Mute);
```

## -see-also

[acxelements.h header](index.md)

