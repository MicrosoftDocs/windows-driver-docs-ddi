---
UID: NF:dbgmodel.IDebugHostField2.GetOffset
tech.root: debugger
title: IDebugHostField2::GetOffset
ms.date: 01/29/2025
targetos: Windows
description: For fields which have an offset, the GetOffset method will return the offset from the base address of the containing type to the data for the field itself.
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
 - IDebugHostField2::GetOffset
f1_keywords:
 - IDebugHostField2::GetOffset
 - dbgmodel/IDebugHostField2::GetOffset
dev_langs:
 - c++
helpviewer_keywords:
 - GetOffset
---

## -description

For fields which have an offset (e.g. fields whose location kind indicates LocationMember), the GetOffset method will return the offset from the base address of the containing type (the this pointer) to the data for the field itself. Such offsets are always expressed as unsigned 64-bit values.

If the given field does not have a location which is an offset from the base address of the containing type, the GetOffset method will fail.

## -parameters

### -param offset

The offset of the field data from the base address of the containing type (e.g.: the this pointer) will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

```cpp
ComPtr<IDebugHostField> spField; /* get a field symbol (see EnumerateChildren) */

ULONG64 fieldOffset;
if (SUCCEEDED(spField->GetOffset(&fieldOffset)))
{
    // For locations which have offsets (as indicated by GetLocationKind), 
    // fieldOffset will contain the offset of the field from the start 
    // of its containing type.
}
```

## -see-also

[IDebugHostField2 interface](nn-dbgmodel-idebughostfield2.md)
