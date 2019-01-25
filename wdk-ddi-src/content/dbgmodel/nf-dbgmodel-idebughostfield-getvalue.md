---
UID: NF:dbgmodel.IDebugHostField.GetValue
title: IDebugHostField::GetValue (dbgmodel.h)
description: For fields which have a constant value defined within the symbolic information, the GetValue method will return the constant value of the field. 
ms.assetid: 1ecd00e7-869f-4e87-8c2f-3d4abea74698
ms.date: 09/12/2018
ms.topic: method
ms.keywords: IDebugHostField::GetValue, GetValue, IDebugHostField.GetValue, IDebugHostField::GetValue, IDebugHostField.GetValue
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
-	IDebugHostField.GetValue
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostField::GetValue


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

[IDebugHostField interface](nn-dbgmodel-idebughostfield.md)
