---
UID: NF:dbgmodel.IDebugHostBaseClass2.GetVirtualBaseOffsetLocation
tech.root: debugger
title: IDebugHostBaseClass2::GetVirtualBaseOffsetLocation
ms.date: 12/16/2024
targetos: Windows
description: The GetVirtualBaseOffsetLocation method returns the location of the "offset" of the base class relative to the parent class. 
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
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
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass2::GetVirtualBaseOffsetLocation
f1_keywords:
 - IDebugHostBaseClass2::GetVirtualBaseOffsetLocation
 - dbgmodel/IDebugHostBaseClass2::GetVirtualBaseOffsetLocation
dev_langs:
 - c++
helpviewer_keywords:
 - GetVirtualBaseOffsetLocation
---

## -description

The GetVirtualBaseOffsetLocation method retrieves the location of the "offset" of the base class relative to the parent class. It provides information necessary to calculate the virtual table (vtbl or vbtbl) location and the corresponding offset within the base class.

## parameters
 

### parameter pTableOffset
 
A pointer to a LONG64 that will receive the offset for the virtual table of the base class relative to the parent class.

### parameter pSlotOffset
 
A pointer to a LONG64 that will receive the offset within the virtual table.

### parameter pSlotSize
 
A pointer to an ULONG64 that will receive the size of the slot in the virtual table.

### parameter pSlotIsSigned
 
A pointer to a boolean that indicates whether the offset read from the slot should be considered a signed or unsigned value.

## -remarks

The location of the vtbl/vbtbl is `(<object> + *pTableOffset)` and the location of the offset within that table is given as `(v[b]tbl + pSlotOffset)`.

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)