---
UID: NF:dbgmodel.IDebugHostField2.GetValue
tech.root: debugger
title: IDebugHostField2::GetValue
ms.date: 01/29/2025
targetos: Windows
description: For fields which have a constant value defined within the symbolic information, the GetValue method will return the constant value of the field.
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
 - IDebugHostField2::GetValue
f1_keywords:
 - IDebugHostField2::GetValue
 - dbgmodel/IDebugHostField2::GetValue
dev_langs:
 - c++
helpviewer_keywords:
 - GetValue
---

## -description

For fields which have a constant value defined within the symbolic information (e.g.: fields whose location kind indicates LocationConstant), the GetValue method will return the constant value of the field. 

If the given field does not have a constant value, the GetValue method will fail.

## -parameters

### -param value

The value of the field packed into a VARIANT will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostField> spField; /* get a field (see EnumerateChildren) */

VARIANT vtValue;
if (SUCCEEDED(spField->GetValue(&vtValue)))
{
    // For fields which have a constant value as determined by GetLocationKind, 
    // vtValue will contain the value of the field.
    VariantClear(&vtValue);
}
```

## -see-also

[IDebugHostField2 interface](nn-dbgmodel-idebughostfield2.md)
