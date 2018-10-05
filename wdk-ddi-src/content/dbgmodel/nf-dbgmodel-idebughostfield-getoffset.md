---
UID: NF:dbgmodel.IDebugHostField.GetOffset
title: IDebugHostField::GetOffset
author: windows-driver-content
description: For fields which have an offset, the GetOffset method will return the offset from the base address of the containing type to the data for the field itself.
ms.assetid: a93e26a7-1ffe-4702-90bd-7fbd93d3e605
ms.author: windowsdriverdev
ms.date: 09/12/2018 
ms.topic: method
ms.keywords: IDebugHostField::GetOffset, GetOffset, IDebugHostField.GetOffset, IDebugHostField::GetOffset, IDebugHostField.GetOffset
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
topic_type: 
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostField.GetOffset
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostField::GetOffset


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

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)
