---
UID: NF:dbgmodel.IDebugHostType2.GetBitField
title: IDebugHostType2::GetBitField (dbgmodel.h)
description: If a given member of a data structure is a bitfield (e.g. ULONG MyBits:8), the type information for the field carries with it information about the bitfield placement.
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetBitField"]
ms.keywords: IDebugHostType2::GetBitField, GetBitField, IDebugHostType2.GetBitField, IDebugHostType2::GetBitField, IDebugHostType2.GetBitField
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostType2::GetBitField
 - dbgmodel/IDebugHostType2::GetBitField
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2::GetBitField
---

# IDebugHostType2::GetBitField


## -description

If a given member of a data structure is a bitfield (e.g.: ULONG MyBits:8), the type information for the field carries with it information about the bitfield placement. The GetBitField method can be used to retrieve that information. This method will fail on any type which is not a bitfield. This is the only reason the method will fail. Simply calling this method and looking at success/failure is sufficient to distinguish a bit field from a non-bit field.

If a given type does happen to be a bitfield, the field positions are defined by the half open set (lsbOfField + lengthOfField : lsbOfField]

## -parameters

### -param lsbOfField

Indicates the least significant bit of the field (where 0 is defined to be the least significant bit of the containing type). The bit field is defined to utilize bits from this point towards the most significant bit of the containing type according to the length specified by the lengthOfField argument.

### -param lengthOfField

The number of bits in the field. This will be at least one and no more than the number of bits in the containing type. The bit field occupies from the bit specified in the lsbOfField argument upwards towards the most significant bit of the containing value according to the number of bits returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get the type of a field which is a bitmap */

ULONG lsb;
ULONG length;
if (SUCCEEDED(spType->GetBitField(&lsb, &length)))
{
    // spType refers to a bitfield.  The field is [lsb, lsb + length) in 
    // bit positions.  Were you to read memory at the location/size specified 
    // by an object of this type, you would need to mask off bits at and 
    // above 'lsb + length' and shift right by 'lsb'
    //
    // Note that IModelObject::GetRawObject will automatically do this for you. 
    // So will creating an object with this type spType via CreateTypedObject.
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

